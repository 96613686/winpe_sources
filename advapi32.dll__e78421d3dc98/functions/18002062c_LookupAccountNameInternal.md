# LookupAccountNameInternal

- ea: `0x18002062c`
- end: `0x1800208e8`
- name: `LookupAccountNameInternal`
- size: `700`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, PCWSTR@<rdx>, PSID pDestinationSid@<r8>, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800250f0`
- `0x1800255a0`

## callees

- `0x180020088`
- `0x180020234`
- `0x18002062c`
- `0x1800208f0`
- `0x180065090`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18002078c`
- `ntdll!RtlLengthSid` at `0x18002078c`
- `ntdll!RtlCopyUnicodeString` at `0x180020866`
- `ntdll!RtlCopyUnicodeString` at `0x180020866`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180020809`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180020809`
- `ntdll!RtlInitUnicodeString` at `0x1800206f7`
- `ntdll!RtlInitUnicodeString` at `0x180020892`
- `ntdll!RtlInitUnicodeString` at `0x1800206f7`
- `ntdll!RtlInitUnicodeString` at `0x180020892`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020827`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180020827`
- `KERNEL32!LocalFree` at `0x1800207bc`
- `KERNEL32!LocalFree` at `0x1800207c5`
- `KERNEL32!LocalFree` at `0x1800208a5`
- `KERNEL32!LocalFree` at `0x1800208cc`
- `KERNEL32!LocalFree` at `0x1800207bc`
- `KERNEL32!LocalFree` at `0x1800207c5`
- `KERNEL32!LocalFree` at `0x1800208a5`
- `KERNEL32!LocalFree` at `0x1800208cc`
- `KERNEL32!BaseSetLastNTError` at `0x1800207aa`
- `KERNEL32!BaseSetLastNTError` at `0x1800208ad`
- `KERNEL32!BaseSetLastNTError` at `0x1800207aa`
- `KERNEL32!BaseSetLastNTError` at `0x1800208ad`

## pseudocode

```c
__int64 __fastcall LookupAccountNameInternal(
        PCWSTR SourceString,
        PCWSTR a2,
        PSID pDestinationSid,
        DWORD *a4,
        WCHAR *a5,
        ULONG *a6,
        _DWORD *a7,
        int a8)
{
  unsigned int v11; // esi
  struct _UNICODE_STRING *v13; // rcx
  NTSTATUS v14; // eax
  int v15; // ebx
  PSID *v16; // rbx
  __int64 v17; // rax
  ULONG v18; // r9d
  ULONG v19; // eax
  bool v21; // cf
  USHORT v22; // ax
  __int64 v23; // rcx
  ULONG BytesInMultiByteString; // [rsp+50h] [rbp-A1h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-99h] BYREF
  HLOCAL v26; // [rsp+60h] [rbp-91h] BYREF
  int v27; // [rsp+68h] [rbp-89h] BYREF
  PVOID PolicyHandle; // [rsp+70h] [rbp-81h] BYREF
  struct _UNICODE_STRING v29; // [rsp+78h] [rbp-79h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-69h] BYREF
  struct _UNICODE_STRING v31; // [rsp+B8h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-29h] BYREF
  _DWORD v33[4]; // [rsp+D8h] [rbp-19h] BYREF

  v33[2] = 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  PolicyHandle = 0;
  hMem = 0;
  v11 = 1;
  BytesInMultiByteString = 0;
  v33[0] = 12;
  v13 = 0;
  v33[1] = 2;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  ObjectAttributes.SecurityQualityOfService = v33;
  DestinationString = 0;
  v29 = 0;
  v31 = 0;
  if ( SourceString )
  {
    RtlInitUnicodeString(&v31, SourceString);
    v13 = &v31;
  }
  v14 = LsaOpenPolicy((PLSA_UNICODE_STRING)v13, &ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v14 < 0 )
  {
    v23 = (unsigned int)v14;
LABEL_19:
    BaseSetLastNTError(v23);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  v27 = 0;
  hMem = 0;
  v26 = 0;
  v15 = LsaICLookupNames_0(
          (__int64)PolicyHandle,
          0,
          1u,
          (__int64)&DestinationString,
          &hMem,
          &v26,
          1,
          0,
          (__int64)&v27,
          0);
  LsaClose(PolicyHandle);
  if ( v15 < 0 )
  {
    if ( v15 == -1073741709 )
    {
      if ( hMem )
        LocalFree(hMem);
      if ( v26 )
        LocalFree(v26);
    }
    v23 = (unsigned int)v15;
    goto LABEL_19;
  }
  v16 = (PSID *)v26;
  v17 = *((int *)v26 + 4);
  if ( a8 )
    BytesInMultiByteString = *(unsigned __int16 *)(*((_QWORD *)hMem + 1) + 24 * v17) >> 1;
  else
    RtlUnicodeToMultiByteSize(
      &BytesInMultiByteString,
      *(PWCH *)(*((_QWORD *)hMem + 1) + 24 * v17 + 8),
      *(unsigned __int16 *)(*((_QWORD *)hMem + 1) + 24 * v17));
  v18 = RtlLengthSid(v16[1]);
  v19 = BytesInMultiByteString;
  if ( v18 > *a4 || BytesInMultiByteString + 1 > *a6 )
  {
    *a4 = v18;
    *a6 = v19 + 1;
    BaseSetLastNTError(3221225507LL);
    v11 = 0;
  }
  else
  {
    CopySid(*a4, pDestinationSid, v16[1]);
    v29.Buffer = a5;
    v21 = *a6 < 0x7FFF;
    v29.Length = 0;
    if ( v21 )
      v22 = 2 * *(_WORD *)a6;
    else
      v22 = -2;
    v29.MaximumLength = v22;
    RtlCopyUnicodeString(&v29, (PCUNICODE_STRING)(*((_QWORD *)hMem + 1) + 24LL * *((int *)v16 + 4)));
    v29.Buffer[(unsigned __int64)v29.Length >> 1] = 0;
    *a7 = *(_DWORD *)v16;
    *a6 = BytesInMultiByteString;
  }
  if ( hMem )
    LocalFree(hMem);
  LocalFree(v16);
  return v11;
}

```

## disassembly

```asm
0x18002062c  push    rbp
0x18002062e  push    rbx
0x18002062f  push    rsi
0x180020630  push    rdi
0x180020631  push    r12
0x180020633  push    r13
0x180020635  push    r14
0x180020637  push    r15
0x180020639  lea     rbp, [rsp-7]
0x18002063e  sub     rsp, 0F8h
0x180020645  mov     rax, cs:__security_cookie
0x18002064c  xor     rax, rsp
0x18002064f  mov     [rbp+3Fh+var_48], rax
0x180020653  mov     r12, [rbp+3Fh+arg_20]
0x180020657  lea     rax, [rbp+3Fh+var_58]
0x18002065b  mov     rdi, [rbp+3Fh+arg_28]
0x18002065f  xorps   xmm0, xmm0
0x180020662  mov     r13, [rbp+3Fh+arg_30]
0x180020666  mov     r15, r8
0x180020669  xor     r8d, r8d
0x18002066c  mov     [rbp+3Fh+var_50], 1
0x180020673  mov     rbx, rdx
0x180020676  mov     qword ptr [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x18002067e  mov     rdx, rcx; SourceString
0x180020681  mov     qword ptr [rbp+3Fh+ObjectAttributes.Attributes], r8
0x180020685  mov     [rsp+130h+PolicyHandle], r8
0x18002068a  xorps   xmm1, xmm1
0x18002068d  mov     [rsp+130h+hMem], r8
0x180020692  lea     esi, [r8+1]
0x180020696  mov     [rsp+130h+BytesInMultiByteString], r8d
0x18002069b  mov     r14, r9
0x18002069e  mov     [rbp+3Fh+var_58], 0Ch
0x1800206a5  mov     ecx, r8d; SystemName
0x1800206a8  mov     [rbp+3Fh+var_54], 2
0x1800206af  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], r8
0x1800206b3  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r8
0x1800206b7  mov     [rbp+3Fh+ObjectAttributes.SecurityDescriptor], r8
0x1800206bb  mov     [rbp+3Fh+ObjectAttributes.SecurityQualityOfService], rax
0x1800206bf  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x1800206c3  movups  xmmword ptr [rbp+3Fh+var_B8.Length], xmm1
0x1800206c7  movups  xmmword ptr [rbp+3Fh+var_78.Length], xmm0
0x1800206cb  test    rdx, rdx
0x1800206ce  jnz     loc_18002088E
0x1800206d4  lea     r9, [rsp+130h+PolicyHandle]; PolicyHandle
0x1800206d9  mov     r8d, 800h; DesiredAccess
0x1800206df  lea     rdx, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1800206e3  call    LsaOpenPolicy
0x1800206e8  test    eax, eax
0x1800206ea  js      loc_1800208A1
0x1800206f0  mov     rdx, rbx; SourceString
0x1800206f3  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800206f7  call    cs:__imp_RtlInitUnicodeString
0x1800206fd  xor     ecx, ecx
0x1800206ff  lea     rax, [rsp+130h+var_C8]
0x180020704  mov     [rsp+130h+var_E8], rcx
0x180020709  lea     r9, [rbp+3Fh+DestinationString]
0x18002070d  mov     [rsp+130h+var_F0], rax
0x180020712  mov     r8d, esi
0x180020715  mov     [rsp+130h+var_F8], ecx
0x180020719  lea     rax, [rsp+130h+var_D0]
0x18002071e  mov     [rsp+130h+var_100], esi
0x180020722  xor     edx, edx
0x180020724  mov     [rsp+130h+var_108], rax
0x180020729  lea     rax, [rsp+130h+hMem]
0x18002072e  mov     [rsp+130h+var_C8], ecx
0x180020732  mov     [rsp+130h+hMem], rcx
0x180020737  mov     [rsp+130h+var_D0], rcx
0x18002073c  mov     rcx, [rsp+130h+PolicyHandle]
0x180020741  mov     [rsp+130h+var_110], rax
0x180020746  call    LsaICLookupNames_0
0x18002074b  mov     rcx, [rsp+130h+PolicyHandle]; ObjectHandle
0x180020750  mov     ebx, eax
0x180020752  call    LsaClose
0x180020757  test    ebx, ebx
0x180020759  js      loc_1800208BA
0x18002075f  cmp     [rbp+3Fh+arg_38], 0
0x180020766  mov     rbx, [rsp+130h+var_D0]
0x18002076b  movsxd  rax, dword ptr [rbx+10h]
0x18002076f  jz      short loc_1800207ED
0x180020771  lea     rdx, [rax+rax*2]
0x180020775  mov     rax, [rsp+130h+hMem]
0x18002077a  mov     rcx, [rax+8]
0x18002077e  movzx   eax, word ptr [rcx+rdx*8]
0x180020782  shr     eax, 1
0x180020784  mov     [rsp+130h+BytesInMultiByteString], eax
0x180020788  mov     rcx, [rbx+8]; Sid
0x18002078c  call    cs:__imp_RtlLengthSid
0x180020792  mov     r9d, eax
0x180020795  mov     eax, [rsp+130h+BytesInMultiByteString]
0x180020799  cmp     r9d, [r14]
0x18002079c  jbe     short loc_180020814
0x18002079e  inc     eax
0x1800207a0  mov     [r14], r9d
0x1800207a3  mov     ecx, 0C0000023h
0x1800207a8  mov     [rdi], eax
0x1800207aa  call    cs:__imp_BaseSetLastNTError
0x1800207b0  xor     esi, esi
0x1800207b2  mov     rcx, [rsp+130h+hMem]; hMem
0x1800207b7  test    rcx, rcx
0x1800207ba  jz      short loc_1800207C2
0x1800207bc  call    cs:__imp_LocalFree
0x1800207c2  mov     rcx, rbx; hMem
0x1800207c5  call    cs:__imp_LocalFree
0x1800207cb  mov     eax, esi
0x1800207cd  mov     rcx, [rbp+3Fh+var_48]
0x1800207d1  xor     rcx, rsp; StackCookie
0x1800207d4  call    __security_check_cookie
0x1800207d9  add     rsp, 0F8h
0x1800207e0  pop     r15
0x1800207e2  pop     r14
0x1800207e4  pop     r13
0x1800207e6  pop     r12
0x1800207e8  pop     rdi
0x1800207e9  pop     rsi
0x1800207ea  pop     rbx
0x1800207eb  pop     rbp
0x1800207ec  retn
0x1800207ed  lea     rcx, [rax+rax*2]
0x1800207f1  mov     rax, [rsp+130h+hMem]
0x1800207f6  mov     rdx, [rax+8]
0x1800207fa  movzx   r8d, word ptr [rdx+rcx*8]; BytesInUnicodeString
0x1800207ff  mov     rdx, [rdx+rcx*8+8]; UnicodeString
0x180020804  lea     rcx, [rsp+130h+BytesInMultiByteString]; BytesInMultiByteString
0x180020809  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18002080f  jmp     loc_180020788
0x180020814  lea     r8d, [rax+1]
0x180020818  cmp     r8d, [rdi]
0x18002081b  ja      short loc_18002079E
0x18002081d  mov     r8, [rbx+8]; pSourceSid
0x180020821  mov     rdx, r15; pDestinationSid
0x180020824  mov     ecx, [r14]; nDestinationSidLength
0x180020827  call    cs:__imp_CopySid
0x18002082d  xor     eax, eax
0x18002082f  mov     [rbp+3Fh+var_B8.Buffer], r12
0x180020833  cmp     dword ptr [rdi], 7FFFh
0x180020839  mov     [rbp+3Fh+var_B8.Length], ax
0x18002083d  jnb     loc_1800208DE
0x180020843  movzx   eax, word ptr [rdi]
0x180020846  add     ax, ax
0x180020849  mov     [rbp+3Fh+var_B8.MaximumLength], ax
0x18002084d  movsxd  rax, dword ptr [rbx+10h]
0x180020851  lea     rdx, [rax+rax*2]
0x180020855  mov     rax, [rsp+130h+hMem]
0x18002085a  mov     rcx, [rax+8]
0x18002085e  lea     rdx, [rcx+rdx*8]; SourceString
0x180020862  lea     rcx, [rbp+3Fh+var_B8]; DestinationString
0x180020866  call    cs:__imp_RtlCopyUnicodeString
0x18002086c  movzx   edx, [rbp+3Fh+var_B8.Length]
0x180020870  mov     rax, [rbp+3Fh+var_B8.Buffer]
0x180020874  shr     rdx, 1
0x180020877  xor     ecx, ecx
0x180020879  mov     [rax+rdx*2], cx
0x18002087d  mov     eax, [rbx]
0x18002087f  mov     [r13+0], eax
0x180020883  mov     eax, [rsp+130h+BytesInMultiByteString]
0x180020887  mov     [rdi], eax
0x180020889  jmp     loc_1800207B2
0x18002088e  lea     rcx, [rbp+3Fh+var_78]; DestinationString
0x180020892  call    cs:__imp_RtlInitUnicodeString
0x180020898  lea     rcx, [rbp+3Fh+var_78]
0x18002089c  jmp     loc_1800206D4
0x1800208a1  mov     ecx, eax
0x1800208a3  jmp     short loc_1800208AD
0x1800208a5  call    cs:__imp_LocalFree
0x1800208ab  mov     ecx, ebx
0x1800208ad  call    cs:__imp_BaseSetLastNTError
0x1800208b3  xor     eax, eax
0x1800208b5  jmp     loc_1800207CD
0x1800208ba  cmp     ebx, 0C0000073h
0x1800208c0  jnz     short loc_1800208AB
0x1800208c2  mov     rcx, [rsp+130h+hMem]; hMem
0x1800208c7  test    rcx, rcx
0x1800208ca  jz      short loc_1800208D2
0x1800208cc  call    cs:__imp_LocalFree
0x1800208d2  mov     rcx, [rsp+130h+var_D0]; hMem
0x1800208d7  test    rcx, rcx
0x1800208da  jz      short loc_1800208AB
0x1800208dc  jmp     short loc_1800208A5
0x1800208de  mov     eax, 0FFFEh
0x1800208e3  jmp     loc_180020849
```
