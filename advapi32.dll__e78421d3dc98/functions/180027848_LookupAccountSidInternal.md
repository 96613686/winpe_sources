# LookupAccountSidInternal

- ea: `0x180027848`
- end: `0x180027bf5`
- name: `LookupAccountSidInternal`
- size: `941`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025320`
- `0x180025640`

## callees

- `0x180020088`
- `0x180020234`
- `0x180027848`
- `0x180027de4`
- `0x180065042`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x180027b0f`
- `ntdll!RtlCopyUnicodeString` at `0x180027b6a`
- `ntdll!RtlCopyUnicodeString` at `0x180027b0f`
- `ntdll!RtlCopyUnicodeString` at `0x180027b6a`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180027a57`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180027a7d`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180027a57`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x180027a7d`
- `ntdll!RtlInitUnicodeString` at `0x1800278fe`
- `ntdll!RtlInitUnicodeString` at `0x1800278fe`
- `KERNELBASE!LocalAlloc` at `0x18002798e`
- `KERNELBASE!LocalAlloc` at `0x18002798e`
- `KERNEL32!LocalFree` at `0x1800279e7`
- `KERNEL32!LocalFree` at `0x1800279fa`
- `KERNEL32!LocalFree` at `0x180027a25`
- `KERNEL32!LocalFree` at `0x180027a33`
- `KERNEL32!LocalFree` at `0x180027bbc`
- `KERNEL32!LocalFree` at `0x180027bcc`
- `KERNEL32!LocalFree` at `0x1800279e7`
- `KERNEL32!LocalFree` at `0x1800279fa`
- `KERNEL32!LocalFree` at `0x180027a25`
- `KERNEL32!LocalFree` at `0x180027a33`
- `KERNEL32!LocalFree` at `0x180027bbc`
- `KERNEL32!LocalFree` at `0x180027bcc`
- `KERNEL32!BaseSetLastNTError` at `0x180027922`
- `KERNEL32!BaseSetLastNTError` at `0x180027bab`
- `KERNEL32!BaseSetLastNTError` at `0x180027922`
- `KERNEL32!BaseSetLastNTError` at `0x180027bab`

## pseudocode

```c
__int64 __fastcall LookupAccountSidInternal(
        PCWSTR SourceString,
        __int64 a2,
        WCHAR *a3,
        ULONG *a4,
        WCHAR *a5,
        _WORD *a6,
        __int64 a7,
        int a8)
{
  struct _UNICODE_STRING *p_DestinationString; // rcx
  unsigned int v11; // r12d
  NTSTATUS v12; // eax
  __int64 v13; // rcx
  int v15; // eax
  char *v16; // r14
  int v17; // esi
  __int64 v18; // rbx
  char *v19; // rax
  char *v20; // rdi
  ULONG v21; // r8d
  ULONG v22; // ecx
  ULONG v23; // r8d
  ULONG v24; // r8d
  bool v25; // zf
  _DWORD *v26; // rcx
  ULONG v27; // [rsp+50h] [rbp-B0h] BYREF
  ULONG BytesInMultiByteString; // [rsp+54h] [rbp-ACh] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v30; // [rsp+60h] [rbp-A0h] BYREF
  int v31; // [rsp+70h] [rbp-90h] BYREF
  PVOID PolicyHandle; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v33; // [rsp+80h] [rbp-80h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  WCHAR *v35; // [rsp+90h] [rbp-70h]
  WCHAR *v36; // [rsp+98h] [rbp-68h]
  __int64 v37; // [rsp+A0h] [rbp-60h]
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  _DWORD v40[4]; // [rsp+E8h] [rbp-18h] BYREF

  v36 = a5;
  v37 = a7;
  ObjectAttributes.SecurityQualityOfService = v40;
  v35 = a3;
  p_DestinationString = 0;
  v34 = a2;
  v11 = 1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  PolicyHandle = 0;
  hMem = 0;
  v27 = 0;
  BytesInMultiByteString = 0;
  v40[2] = 1;
  v40[0] = 12;
  v40[1] = 2;
  memset(&ObjectAttributes.RootDirectory, 0, 32);
  v30 = 0;
  DestinationString = 0;
  if ( SourceString )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    p_DestinationString = &DestinationString;
  }
  v12 = LsaOpenPolicy((PLSA_UNICODE_STRING)p_DestinationString, &ObjectAttributes, 0x800u, &PolicyHandle);
  if ( v12 < 0 )
  {
    v13 = (unsigned int)v12;
LABEL_5:
    BaseSetLastNTError(v13);
    return 0;
  }
  v31 = 0;
  v33 = 0;
  v15 = LsaICLookupSids_0(
          (_DWORD)PolicyHandle,
          1,
          (unsigned int)&v34,
          (unsigned int)&hMem,
          (__int64)&v33,
          1,
          0,
          (__int64)&v31,
          0);
  v16 = (char *)v33;
  v17 = v15;
  if ( v33 )
  {
    _mm_lfence();
    v18 = *((unsigned __int16 *)v33 + 5);
    v19 = (char *)LocalAlloc(0x40u, v18 + 32);
    v20 = v19;
    if ( v19 )
    {
      memset_0(v19, 0, v18 + 32);
      *(_DWORD *)v20 = *(_DWORD *)v16;
      *((_DWORD *)v20 + 6) = *((_DWORD *)v16 + 6);
      *(_OWORD *)(v20 + 8) = *(_OWORD *)(v16 + 8);
      memcpy_0(v20 + 32, *((const void **)v16 + 2), *((unsigned __int16 *)v16 + 4));
      *((_QWORD *)v20 + 2) = v20 + 32;
    }
    else
    {
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      v17 = -1073741670;
    }
    LocalFree(v16);
  }
  else
  {
    v20 = 0;
  }
  LsaClose(PolicyHandle);
  if ( v17 < 0 )
  {
    if ( v17 == -1073741709 )
    {
      if ( hMem )
        LocalFree(hMem);
      if ( v20 )
        LocalFree(v20);
    }
    v13 = (unsigned int)v17;
    goto LABEL_5;
  }
  v21 = *((unsigned __int16 *)v20 + 4);
  if ( a8 )
  {
    v23 = v21 >> 1;
    BytesInMultiByteString = v23;
    v22 = *(unsigned __int16 *)(*((_QWORD *)hMem + 1) + 24LL * *((int *)v20 + 6)) >> 1;
    v27 = v22;
  }
  else
  {
    RtlUnicodeToMultiByteSize(&BytesInMultiByteString, *((PWCH *)v20 + 2), v21);
    RtlUnicodeToMultiByteSize(
      &v27,
      *(PWCH *)(*((_QWORD *)hMem + 1) + 24LL * *((int *)v20 + 6) + 8),
      *(unsigned __int16 *)(*((_QWORD *)hMem + 1) + 24LL * *((int *)v20 + 6)));
    v22 = v27;
    v23 = BytesInMultiByteString;
  }
  v24 = v23 + 1;
  if ( v24 <= *a4 && v22 + 1 <= *(_DWORD *)a6 )
  {
    v30.Buffer = v35;
    v30.Length = 0;
    if ( *a4 > 0x7FFF )
    {
      v30.MaximumLength = -2;
    }
    else
    {
      v25 = *a4 == 0;
      v30.MaximumLength = 2 * *(_WORD *)a4;
      if ( v25 )
        goto LABEL_31;
    }
    RtlCopyUnicodeString(&v30, (PCUNICODE_STRING)(v20 + 8));
    v30.Buffer[(unsigned __int64)v30.Length >> 1] = 0;
LABEL_31:
    v30.Buffer = v36;
    v30.Length = 0;
    if ( *(_DWORD *)a6 > 0x7FFFu )
      v30.MaximumLength = -2;
    else
      v30.MaximumLength = 2 * *a6;
    RtlCopyUnicodeString(&v30, (PCUNICODE_STRING)(*((_QWORD *)hMem + 1) + 24LL * *((int *)v20 + 6)));
    v30.Buffer[(unsigned __int64)v30.Length >> 1] = 0;
    v26 = (_DWORD *)v37;
    *(_DWORD *)a6 = v27;
    *a4 = BytesInMultiByteString;
    *v26 = *(_DWORD *)v20;
    goto LABEL_36;
  }
  *(_DWORD *)a6 = v22 + 1;
  *a4 = v24;
  BaseSetLastNTError(3221225507LL);
  v11 = 0;
LABEL_36:
  if ( v20 )
    LocalFree(v20);
  if ( hMem )
    LocalFree(hMem);
  return v11;
}

```

## disassembly

```asm
0x180027848  push    rbp
0x18002784a  push    rbx
0x18002784b  push    rsi
0x18002784c  push    rdi
0x18002784d  push    r12
0x18002784f  push    r13
0x180027851  push    r14
0x180027853  push    r15
0x180027855  lea     rbp, [rsp-8]
0x18002785a  sub     rsp, 108h
0x180027861  mov     rax, cs:__security_cookie
0x180027868  xor     rax, rsp
0x18002786b  mov     [rbp+40h+var_48], rax
0x18002786f  mov     rax, [rbp+40h+arg_20]
0x180027873  xor     ebx, ebx
0x180027875  mov     r15, [rbp+40h+arg_28]
0x180027879  mov     r10, rcx
0x18002787c  mov     [rbp+40h+var_A8], rax
0x180027880  xorps   xmm0, xmm0
0x180027883  mov     rax, [rbp+40h+arg_30]
0x18002788a  xorps   xmm1, xmm1
0x18002788d  mov     [rbp+40h+var_A0], rax
0x180027891  lea     rax, [rbp+40h+var_58]
0x180027895  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x180027899  mov     r13, r9
0x18002789c  mov     [rbp+40h+var_B0], r8
0x1800278a0  mov     ecx, ebx
0x1800278a2  mov     [rbp+40h+var_B8], rdx
0x1800278a6  lea     r12d, [rbx+1]
0x1800278aa  mov     qword ptr [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x1800278b2  mov     qword ptr [rbp+40h+ObjectAttributes.Attributes], rbx
0x1800278b6  mov     [rsp+140h+PolicyHandle], rbx
0x1800278bb  mov     [rsp+140h+hMem], rbx
0x1800278c0  mov     [rsp+140h+var_F0], ebx
0x1800278c4  mov     [rsp+140h+BytesInMultiByteString], ebx
0x1800278c8  mov     [rbp+40h+var_50], 1
0x1800278cf  mov     [rbp+40h+var_58], 0Ch
0x1800278d6  mov     [rbp+40h+var_54], 2
0x1800278dd  mov     [rbp+40h+ObjectAttributes.RootDirectory], rbx
0x1800278e1  mov     [rbp+40h+ObjectAttributes.ObjectName], rbx
0x1800278e5  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rbx
0x1800278e9  movups  xmmword ptr [rsp+140h+var_E0.Length], xmm0
0x1800278ee  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm1
0x1800278f2  test    r10, r10
0x1800278f5  jz      short loc_180027908
0x1800278f7  mov     rdx, r10; SourceString
0x1800278fa  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x1800278fe  call    cs:__imp_RtlInitUnicodeString
0x180027904  lea     rcx, [rbp+40h+DestinationString]; SystemName
0x180027908  lea     r9, [rsp+140h+PolicyHandle]; PolicyHandle
0x18002790d  mov     r8d, 800h; DesiredAccess
0x180027913  lea     rdx, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x180027917  call    LsaOpenPolicy
0x18002791c  test    eax, eax
0x18002791e  jns     short loc_18002792F
0x180027920  mov     ecx, eax
0x180027922  call    cs:__imp_BaseSetLastNTError
0x180027928  xor     eax, eax
0x18002792a  jmp     loc_180027BD5
0x18002792f  mov     rcx, [rsp+140h+PolicyHandle]
0x180027934  lea     rax, [rsp+140h+var_D0]
0x180027939  mov     [rsp+140h+var_100], rbx
0x18002793e  lea     r9, [rsp+140h+hMem]
0x180027943  mov     [rsp+140h+var_108], rax
0x180027948  lea     r8, [rbp+40h+var_B8]
0x18002794c  mov     [rsp+140h+var_110], ebx
0x180027950  lea     rax, [rbp+40h+var_C0]
0x180027954  mov     [rsp+140h+var_118], r12d
0x180027959  mov     edx, r12d
0x18002795c  mov     [rsp+140h+var_120], rax
0x180027961  mov     [rsp+140h+var_D0], ebx
0x180027965  mov     [rbp+40h+var_C0], rbx
0x180027969  call    LsaICLookupSids_0
0x18002796e  mov     r14, [rbp+40h+var_C0]
0x180027972  mov     esi, eax
0x180027974  test    r14, r14
0x180027977  jz      loc_180027A02
0x18002797d  lfence
0x180027980  movzx   ebx, word ptr [r14+0Ah]
0x180027985  mov     ecx, 40h ; '@'; uFlags
0x18002798a  lea     rdx, [rbx+20h]; uBytes
0x18002798e  call    cs:__imp_LocalAlloc
0x180027994  mov     rdi, rax
0x180027997  test    rax, rax
0x18002799a  jz      short loc_1800279DB
0x18002799c  lea     r8, [rbx+20h]; Size
0x1800279a0  xor     edx, edx; Val
0x1800279a2  mov     rcx, rax; void *
0x1800279a5  call    memset_0
0x1800279aa  mov     eax, [r14]
0x1800279ad  lea     rbx, [rdi+20h]
0x1800279b1  mov     [rdi], eax
0x1800279b3  mov     rcx, rbx; void *
0x1800279b6  mov     eax, [r14+18h]
0x1800279ba  mov     [rdi+18h], eax
0x1800279bd  movups  xmm0, xmmword ptr [r14+8]
0x1800279c2  movdqu  xmmword ptr [rdi+8], xmm0
0x1800279c7  movzx   r8d, word ptr [r14+8]; Size
0x1800279cc  mov     rdx, [r14+10h]; Src
0x1800279d0  call    memcpy_0
0x1800279d5  mov     [rdi+10h], rbx
0x1800279d9  jmp     short loc_1800279F7
0x1800279db  mov     rcx, [rsp+140h+hMem]; hMem
0x1800279e0  xor     ebx, ebx
0x1800279e2  test    rcx, rcx
0x1800279e5  jz      short loc_1800279F2
0x1800279e7  call    cs:__imp_LocalFree
0x1800279ed  mov     [rsp+140h+hMem], rbx
0x1800279f2  mov     esi, 0C000009Ah
0x1800279f7  mov     rcx, r14; hMem
0x1800279fa  call    cs:__imp_LocalFree
0x180027a00  jmp     short loc_180027A05
0x180027a02  mov     rdi, rbx
0x180027a05  mov     rcx, [rsp+140h+PolicyHandle]; ObjectHandle
0x180027a0a  call    LsaClose
0x180027a0f  test    esi, esi
0x180027a11  jns     short loc_180027A40
0x180027a13  cmp     esi, 0C0000073h
0x180027a19  jnz     short loc_180027A39
0x180027a1b  mov     rcx, [rsp+140h+hMem]; hMem
0x180027a20  test    rcx, rcx
0x180027a23  jz      short loc_180027A2B
0x180027a25  call    cs:__imp_LocalFree
0x180027a2b  test    rdi, rdi
0x180027a2e  jz      short loc_180027A39
0x180027a30  mov     rcx, rdi; hMem
0x180027a33  call    cs:__imp_LocalFree
0x180027a39  mov     ecx, esi
0x180027a3b  jmp     loc_180027922
0x180027a40  cmp     [rbp+40h+arg_38], 0
0x180027a47  movzx   r8d, word ptr [rdi+8]; BytesInUnicodeString
0x180027a4c  jnz     short loc_180027A8E
0x180027a4e  mov     rdx, [rdi+10h]; UnicodeString
0x180027a52  lea     rcx, [rsp+140h+BytesInMultiByteString]; BytesInMultiByteString
0x180027a57  call    cs:__imp_RtlUnicodeToMultiByteSize
0x180027a5d  movsxd  rax, dword ptr [rdi+18h]
0x180027a61  lea     rcx, [rax+rax*2]
0x180027a65  mov     rax, [rsp+140h+hMem]
0x180027a6a  mov     rdx, [rax+8]
0x180027a6e  movzx   r8d, word ptr [rdx+rcx*8]; BytesInUnicodeString
0x180027a73  mov     rdx, [rdx+rcx*8+8]; UnicodeString
0x180027a78  lea     rcx, [rsp+140h+var_F0]; BytesInMultiByteString
0x180027a7d  call    cs:__imp_RtlUnicodeToMultiByteSize
0x180027a83  mov     ecx, [rsp+140h+var_F0]
0x180027a87  mov     r8d, [rsp+140h+BytesInMultiByteString]
0x180027a8c  jmp     short loc_180027AB1
0x180027a8e  shr     r8d, 1
0x180027a91  mov     [rsp+140h+BytesInMultiByteString], r8d
0x180027a96  movsxd  rax, dword ptr [rdi+18h]
0x180027a9a  lea     rdx, [rax+rax*2]
0x180027a9e  mov     rax, [rsp+140h+hMem]
0x180027aa3  mov     rcx, [rax+8]
0x180027aa7  movzx   ecx, word ptr [rcx+rdx*8]
0x180027aab  shr     ecx, 1
0x180027aad  mov     [rsp+140h+var_F0], ecx
0x180027ab1  inc     r8d
0x180027ab4  cmp     r8d, [r13+0]
0x180027ab8  ja      loc_180027B9C
0x180027abe  lea     eax, [rcx+1]
0x180027ac1  cmp     eax, [r15]
0x180027ac4  ja      loc_180027B9C
0x180027aca  mov     rax, [rbp+40h+var_B0]
0x180027ace  mov     r14d, 7FFFh
0x180027ad4  mov     [rsp+140h+var_E0.Buffer], rax
0x180027ad9  mov     esi, 0FFFEh
0x180027ade  xor     eax, eax
0x180027ae0  mov     [rsp+140h+var_E0.Length], ax
0x180027ae5  cmp     [r13+0], r14d
0x180027ae9  ja      short loc_180027B01
0x180027aeb  movzx   eax, word ptr [r13+0]
0x180027af0  add     ax, ax
0x180027af3  cmp     dword ptr [r13+0], 0
0x180027af8  mov     [rsp+140h+var_E0.MaximumLength], ax
0x180027afd  ja      short loc_180027B06
0x180027aff  jmp     short loc_180027B28
0x180027b01  mov     [rsp+140h+var_E0.MaximumLength], si
0x180027b06  lea     rdx, [rdi+8]; SourceString
0x180027b0a  lea     rcx, [rsp+140h+var_E0]; DestinationString
0x180027b0f  call    cs:__imp_RtlCopyUnicodeString
0x180027b15  movzx   edx, [rsp+140h+var_E0.Length]
0x180027b1a  mov     rax, [rsp+140h+var_E0.Buffer]
0x180027b1f  shr     rdx, 1
0x180027b22  xor     ecx, ecx
0x180027b24  mov     [rax+rdx*2], cx
0x180027b28  mov     rax, [rbp+40h+var_A8]
0x180027b2c  mov     [rsp+140h+var_E0.Buffer], rax
0x180027b31  xor     eax, eax
0x180027b33  mov     [rsp+140h+var_E0.Length], ax
0x180027b38  cmp     [r15], r14d
0x180027b3b  ja      short loc_180027B4B
0x180027b3d  movzx   eax, word ptr [r15]
0x180027b41  add     ax, ax
0x180027b44  mov     [rsp+140h+var_E0.MaximumLength], ax
0x180027b49  jmp     short loc_180027B50
0x180027b4b  mov     [rsp+140h+var_E0.MaximumLength], si
0x180027b50  movsxd  rax, dword ptr [rdi+18h]
0x180027b54  lea     rdx, [rax+rax*2]
0x180027b58  mov     rax, [rsp+140h+hMem]
0x180027b5d  mov     rcx, [rax+8]
0x180027b61  lea     rdx, [rcx+rdx*8]; SourceString
0x180027b65  lea     rcx, [rsp+140h+var_E0]; DestinationString
0x180027b6a  call    cs:__imp_RtlCopyUnicodeString
0x180027b70  movzx   edx, [rsp+140h+var_E0.Length]
0x180027b75  mov     rax, [rsp+140h+var_E0.Buffer]
0x180027b7a  shr     rdx, 1
0x180027b7d  xor     ecx, ecx
0x180027b7f  mov     [rax+rdx*2], cx
0x180027b83  mov     eax, [rsp+140h+var_F0]
0x180027b87  mov     rcx, [rbp+40h+var_A0]
0x180027b8b  mov     [r15], eax
0x180027b8e  mov     eax, [rsp+140h+BytesInMultiByteString]
0x180027b92  mov     [r13+0], eax
0x180027b96  mov     eax, [rdi]
0x180027b98  mov     [rcx], eax
0x180027b9a  jmp     short loc_180027BB4
0x180027b9c  lea     eax, [rcx+1]
0x180027b9f  mov     ecx, 0C0000023h
0x180027ba4  mov     [r15], eax
0x180027ba7  mov     [r13+0], r8d
0x180027bab  call    cs:__imp_BaseSetLastNTError
0x180027bb1  xor     r12d, r12d
0x180027bb4  test    rdi, rdi
0x180027bb7  jz      short loc_180027BC2
0x180027bb9  mov     rcx, rdi; hMem
0x180027bbc  call    cs:__imp_LocalFree
0x180027bc2  mov     rcx, [rsp+140h+hMem]; hMem
0x180027bc7  test    rcx, rcx
0x180027bca  jz      short loc_180027BD2
0x180027bcc  call    cs:__imp_LocalFree
0x180027bd2  mov     eax, r12d
0x180027bd5  mov     rcx, [rbp+40h+var_48]
0x180027bd9  xor     rcx, rsp; StackCookie
0x180027bdc  call    __security_check_cookie
0x180027be1  add     rsp, 108h
0x180027be8  pop     r15
0x180027bea  pop     r14
0x180027bec  pop     r13
0x180027bee  pop     r12
0x180027bf0  pop     rdi
0x180027bf1  pop     rsi
0x180027bf2  pop     rbx
0x180027bf3  pop     rbp
0x180027bf4  retn
```
