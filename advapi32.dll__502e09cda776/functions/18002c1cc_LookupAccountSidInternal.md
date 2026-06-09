# LookupAccountSidInternal

- ea: `0x18002c1cc`
- end: `0x18002c5ce`
- name: `LookupAccountSidInternal`
- size: `1026`
- prototype: `__int64 __usercall@<rax>(PCWSTR SourceString@<rcx>, __int64, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800279c0`
- `0x180027d50`

## callees

- `0x18001df64`
- `0x18001e120`
- `0x18002c1cc`
- `0x18002c7d4`
- `0x180072042`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `ntdll!RtlCopyUnicodeString` at `0x18002c4c9`
- `ntdll!RtlCopyUnicodeString` at `0x18002c52a`
- `ntdll!RtlCopyUnicodeString` at `0x18002c4c9`
- `ntdll!RtlCopyUnicodeString` at `0x18002c52a`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18002c405`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18002c431`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18002c405`
- `ntdll!RtlUnicodeToMultiByteSize` at `0x18002c431`
- `ntdll!RtlInitUnicodeString` at `0x18002c282`
- `ntdll!RtlInitUnicodeString` at `0x18002c282`
- `KERNELBASE!LocalAlloc` at `0x18002c31e`
- `KERNELBASE!LocalAlloc` at `0x18002c31e`
- `KERNEL32!LocalFree` at `0x18002c37d`
- `KERNEL32!LocalFree` at `0x18002c396`
- `KERNEL32!LocalFree` at `0x18002c3c7`
- `KERNEL32!LocalFree` at `0x18002c3db`
- `KERNEL32!LocalFree` at `0x18002c588`
- `KERNEL32!LocalFree` at `0x18002c59e`
- `KERNEL32!LocalFree` at `0x18002c37d`
- `KERNEL32!LocalFree` at `0x18002c396`
- `KERNEL32!LocalFree` at `0x18002c3c7`
- `KERNEL32!LocalFree` at `0x18002c3db`
- `KERNEL32!LocalFree` at `0x18002c588`
- `KERNEL32!LocalFree` at `0x18002c59e`
- `KERNEL32!BaseSetLastNTError` at `0x18002c2ac`
- `KERNEL32!BaseSetLastNTError` at `0x18002c571`
- `KERNEL32!BaseSetLastNTError` at `0x18002c2ac`
- `KERNEL32!BaseSetLastNTError` at `0x18002c571`

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
0x18002c1cc  push    rbp
0x18002c1ce  push    rbx
0x18002c1cf  push    rsi
0x18002c1d0  push    rdi
0x18002c1d1  push    r12
0x18002c1d3  push    r13
0x18002c1d5  push    r14
0x18002c1d7  push    r15
0x18002c1d9  lea     rbp, [rsp-8]
0x18002c1de  sub     rsp, 108h
0x18002c1e5  mov     rax, cs:__security_cookie
0x18002c1ec  xor     rax, rsp
0x18002c1ef  mov     [rbp+40h+var_48], rax
0x18002c1f3  mov     rax, [rbp+40h+arg_20]
0x18002c1f7  xor     ebx, ebx
0x18002c1f9  mov     r15, [rbp+40h+arg_28]
0x18002c1fd  mov     r10, rcx
0x18002c200  mov     [rbp+40h+var_A8], rax
0x18002c204  xorps   xmm0, xmm0
0x18002c207  mov     rax, [rbp+40h+arg_30]
0x18002c20e  xorps   xmm1, xmm1
0x18002c211  mov     [rbp+40h+var_A0], rax
0x18002c215  lea     rax, [rbp+40h+var_58]
0x18002c219  mov     [rbp+40h+ObjectAttributes.SecurityQualityOfService], rax
0x18002c21d  mov     r13, r9
0x18002c220  mov     [rbp+40h+var_B0], r8
0x18002c224  mov     ecx, ebx
0x18002c226  mov     [rbp+40h+var_B8], rdx
0x18002c22a  lea     r12d, [rbx+1]
0x18002c22e  mov     qword ptr [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x18002c236  mov     qword ptr [rbp+40h+ObjectAttributes.Attributes], rbx
0x18002c23a  mov     [rsp+140h+PolicyHandle], rbx
0x18002c23f  mov     [rsp+140h+hMem], rbx
0x18002c244  mov     [rsp+140h+var_F0], ebx
0x18002c248  mov     [rsp+140h+BytesInMultiByteString], ebx
0x18002c24c  mov     [rbp+40h+var_50], 1
0x18002c253  mov     [rbp+40h+var_58], 0Ch
0x18002c25a  mov     [rbp+40h+var_54], 2
0x18002c261  mov     [rbp+40h+ObjectAttributes.RootDirectory], rbx
0x18002c265  mov     [rbp+40h+ObjectAttributes.ObjectName], rbx
0x18002c269  mov     [rbp+40h+ObjectAttributes.SecurityDescriptor], rbx
0x18002c26d  movups  xmmword ptr [rsp+140h+var_E0.Length], xmm0
0x18002c272  movups  xmmword ptr [rbp+40h+DestinationString.Length], xmm1
0x18002c276  test    r10, r10
0x18002c279  jz      short loc_18002C292
0x18002c27b  mov     rdx, r10; SourceString
0x18002c27e  lea     rcx, [rbp+40h+DestinationString]; DestinationString
0x18002c282  call    cs:__imp_RtlInitUnicodeString
0x18002c289  nop     dword ptr [rax+rax+00h]
0x18002c28e  lea     rcx, [rbp+40h+DestinationString]; SystemName
0x18002c292  lea     r9, [rsp+140h+PolicyHandle]; PolicyHandle
0x18002c297  mov     r8d, 800h; DesiredAccess
0x18002c29d  lea     rdx, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x18002c2a1  call    LsaOpenPolicy
0x18002c2a6  test    eax, eax
0x18002c2a8  jns     short loc_18002C2BF
0x18002c2aa  mov     ecx, eax
0x18002c2ac  call    cs:__imp_BaseSetLastNTError
0x18002c2b3  nop     dword ptr [rax+rax+00h]
0x18002c2b8  xor     eax, eax
0x18002c2ba  jmp     loc_18002C5AD
0x18002c2bf  mov     rcx, [rsp+140h+PolicyHandle]
0x18002c2c4  lea     rax, [rsp+140h+var_D0]
0x18002c2c9  mov     [rsp+140h+var_100], rbx
0x18002c2ce  lea     r9, [rsp+140h+hMem]
0x18002c2d3  mov     [rsp+140h+var_108], rax
0x18002c2d8  lea     r8, [rbp+40h+var_B8]
0x18002c2dc  mov     [rsp+140h+var_110], ebx
0x18002c2e0  lea     rax, [rbp+40h+var_C0]
0x18002c2e4  mov     [rsp+140h+var_118], r12d
0x18002c2e9  mov     edx, r12d
0x18002c2ec  mov     [rsp+140h+var_120], rax
0x18002c2f1  mov     [rsp+140h+var_D0], ebx
0x18002c2f5  mov     [rbp+40h+var_C0], rbx
0x18002c2f9  call    LsaICLookupSids_0
0x18002c2fe  mov     r14, [rbp+40h+var_C0]
0x18002c302  mov     esi, eax
0x18002c304  test    r14, r14
0x18002c307  jz      loc_18002C3A4
0x18002c30d  lfence
0x18002c310  movzx   ebx, word ptr [r14+0Ah]
0x18002c315  mov     ecx, 40h ; '@'; uFlags
0x18002c31a  lea     rdx, [rbx+20h]; uBytes
0x18002c31e  call    cs:__imp_LocalAlloc
0x18002c325  nop     dword ptr [rax+rax+00h]
0x18002c32a  mov     rdi, rax
0x18002c32d  test    rax, rax
0x18002c330  jz      short loc_18002C371
0x18002c332  lea     r8, [rbx+20h]; Size
0x18002c336  xor     edx, edx; Val
0x18002c338  mov     rcx, rax; void *
0x18002c33b  call    memset_0
0x18002c340  mov     eax, [r14]
0x18002c343  lea     rbx, [rdi+20h]
0x18002c347  mov     [rdi], eax
0x18002c349  mov     rcx, rbx; void *
0x18002c34c  mov     eax, [r14+18h]
0x18002c350  mov     [rdi+18h], eax
0x18002c353  movups  xmm0, xmmword ptr [r14+8]
0x18002c358  movdqu  xmmword ptr [rdi+8], xmm0
0x18002c35d  movzx   r8d, word ptr [r14+8]; Size
0x18002c362  mov     rdx, [r14+10h]; Src
0x18002c366  call    memcpy_0
0x18002c36b  mov     [rdi+10h], rbx
0x18002c36f  jmp     short loc_18002C393
0x18002c371  mov     rcx, [rsp+140h+hMem]; hMem
0x18002c376  xor     ebx, ebx
0x18002c378  test    rcx, rcx
0x18002c37b  jz      short loc_18002C38E
0x18002c37d  call    cs:__imp_LocalFree
0x18002c384  nop     dword ptr [rax+rax+00h]
0x18002c389  mov     [rsp+140h+hMem], rbx
0x18002c38e  mov     esi, 0C000009Ah
0x18002c393  mov     rcx, r14; hMem
0x18002c396  call    cs:__imp_LocalFree
0x18002c39d  nop     dword ptr [rax+rax+00h]
0x18002c3a2  jmp     short loc_18002C3A7
0x18002c3a4  mov     rdi, rbx
0x18002c3a7  mov     rcx, [rsp+140h+PolicyHandle]; ObjectHandle
0x18002c3ac  call    LsaClose
0x18002c3b1  test    esi, esi
0x18002c3b3  jns     short loc_18002C3EE
0x18002c3b5  cmp     esi, 0C0000073h
0x18002c3bb  jnz     short loc_18002C3E7
0x18002c3bd  mov     rcx, [rsp+140h+hMem]; hMem
0x18002c3c2  test    rcx, rcx
0x18002c3c5  jz      short loc_18002C3D3
0x18002c3c7  call    cs:__imp_LocalFree
0x18002c3ce  nop     dword ptr [rax+rax+00h]
0x18002c3d3  test    rdi, rdi
0x18002c3d6  jz      short loc_18002C3E7
0x18002c3d8  mov     rcx, rdi; hMem
0x18002c3db  call    cs:__imp_LocalFree
0x18002c3e2  nop     dword ptr [rax+rax+00h]
0x18002c3e7  mov     ecx, esi
0x18002c3e9  jmp     loc_18002C2AC
0x18002c3ee  cmp     [rbp+40h+arg_38], 0
0x18002c3f5  movzx   r8d, word ptr [rdi+8]; BytesInUnicodeString
0x18002c3fa  jnz     short loc_18002C448
0x18002c3fc  mov     rdx, [rdi+10h]; UnicodeString
0x18002c400  lea     rcx, [rsp+140h+BytesInMultiByteString]; BytesInMultiByteString
0x18002c405  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18002c40c  nop     dword ptr [rax+rax+00h]
0x18002c411  movsxd  rax, dword ptr [rdi+18h]
0x18002c415  lea     rcx, [rax+rax*2]
0x18002c419  mov     rax, [rsp+140h+hMem]
0x18002c41e  mov     rdx, [rax+8]
0x18002c422  movzx   r8d, word ptr [rdx+rcx*8]; BytesInUnicodeString
0x18002c427  mov     rdx, [rdx+rcx*8+8]; UnicodeString
0x18002c42c  lea     rcx, [rsp+140h+var_F0]; BytesInMultiByteString
0x18002c431  call    cs:__imp_RtlUnicodeToMultiByteSize
0x18002c438  nop     dword ptr [rax+rax+00h]
0x18002c43d  mov     ecx, [rsp+140h+var_F0]
0x18002c441  mov     r8d, [rsp+140h+BytesInMultiByteString]
0x18002c446  jmp     short loc_18002C46B
0x18002c448  shr     r8d, 1
0x18002c44b  mov     [rsp+140h+BytesInMultiByteString], r8d
0x18002c450  movsxd  rax, dword ptr [rdi+18h]
0x18002c454  lea     rdx, [rax+rax*2]
0x18002c458  mov     rax, [rsp+140h+hMem]
0x18002c45d  mov     rcx, [rax+8]
0x18002c461  movzx   ecx, word ptr [rcx+rdx*8]
0x18002c465  shr     ecx, 1
0x18002c467  mov     [rsp+140h+var_F0], ecx
0x18002c46b  inc     r8d
0x18002c46e  cmp     r8d, [r13+0]
0x18002c472  ja      loc_18002C562
0x18002c478  lea     eax, [rcx+1]
0x18002c47b  cmp     eax, [r15]
0x18002c47e  ja      loc_18002C562
0x18002c484  mov     rax, [rbp+40h+var_B0]
0x18002c488  mov     r14d, 7FFFh
0x18002c48e  mov     [rsp+140h+var_E0.Buffer], rax
0x18002c493  mov     esi, 0FFFEh
0x18002c498  xor     eax, eax
0x18002c49a  mov     [rsp+140h+var_E0.Length], ax
0x18002c49f  cmp     [r13+0], r14d
0x18002c4a3  ja      short loc_18002C4BB
0x18002c4a5  movzx   eax, word ptr [r13+0]
0x18002c4aa  add     ax, ax
0x18002c4ad  cmp     dword ptr [r13+0], 0
0x18002c4b2  mov     [rsp+140h+var_E0.MaximumLength], ax
0x18002c4b7  ja      short loc_18002C4C0
0x18002c4b9  jmp     short loc_18002C4E8
0x18002c4bb  mov     [rsp+140h+var_E0.MaximumLength], si
0x18002c4c0  lea     rdx, [rdi+8]; SourceString
0x18002c4c4  lea     rcx, [rsp+140h+var_E0]; DestinationString
0x18002c4c9  call    cs:__imp_RtlCopyUnicodeString
0x18002c4d0  nop     dword ptr [rax+rax+00h]
0x18002c4d5  movzx   edx, [rsp+140h+var_E0.Length]
0x18002c4da  mov     rax, [rsp+140h+var_E0.Buffer]
0x18002c4df  shr     rdx, 1
0x18002c4e2  xor     ecx, ecx
0x18002c4e4  mov     [rax+rdx*2], cx
0x18002c4e8  mov     rax, [rbp+40h+var_A8]
0x18002c4ec  mov     [rsp+140h+var_E0.Buffer], rax
0x18002c4f1  xor     eax, eax
0x18002c4f3  mov     [rsp+140h+var_E0.Length], ax
0x18002c4f8  cmp     [r15], r14d
0x18002c4fb  ja      short loc_18002C50B
0x18002c4fd  movzx   eax, word ptr [r15]
0x18002c501  add     ax, ax
0x18002c504  mov     [rsp+140h+var_E0.MaximumLength], ax
0x18002c509  jmp     short loc_18002C510
0x18002c50b  mov     [rsp+140h+var_E0.MaximumLength], si
0x18002c510  movsxd  rax, dword ptr [rdi+18h]
0x18002c514  lea     rdx, [rax+rax*2]
0x18002c518  mov     rax, [rsp+140h+hMem]
0x18002c51d  mov     rcx, [rax+8]
0x18002c521  lea     rdx, [rcx+rdx*8]; SourceString
0x18002c525  lea     rcx, [rsp+140h+var_E0]; DestinationString
0x18002c52a  call    cs:__imp_RtlCopyUnicodeString
0x18002c531  nop     dword ptr [rax+rax+00h]
0x18002c536  movzx   edx, [rsp+140h+var_E0.Length]
0x18002c53b  mov     rax, [rsp+140h+var_E0.Buffer]
0x18002c540  shr     rdx, 1
0x18002c543  xor     ecx, ecx
0x18002c545  mov     [rax+rdx*2], cx
0x18002c549  mov     eax, [rsp+140h+var_F0]
0x18002c54d  mov     rcx, [rbp+40h+var_A0]
0x18002c551  mov     [r15], eax
0x18002c554  mov     eax, [rsp+140h+BytesInMultiByteString]
0x18002c558  mov     [r13+0], eax
0x18002c55c  mov     eax, [rdi]
0x18002c55e  mov     [rcx], eax
0x18002c560  jmp     short loc_18002C580
0x18002c562  lea     eax, [rcx+1]
0x18002c565  mov     ecx, 0C0000023h
0x18002c56a  mov     [r15], eax
0x18002c56d  mov     [r13+0], r8d
0x18002c571  call    cs:__imp_BaseSetLastNTError
0x18002c578  nop     dword ptr [rax+rax+00h]
0x18002c57d  xor     r12d, r12d
0x18002c580  test    rdi, rdi
0x18002c583  jz      short loc_18002C594
0x18002c585  mov     rcx, rdi; hMem
0x18002c588  call    cs:__imp_LocalFree
0x18002c58f  nop     dword ptr [rax+rax+00h]
0x18002c594  mov     rcx, [rsp+140h+hMem]; hMem
0x18002c599  test    rcx, rcx
0x18002c59c  jz      short loc_18002C5AA
0x18002c59e  call    cs:__imp_LocalFree
0x18002c5a5  nop     dword ptr [rax+rax+00h]
0x18002c5aa  mov     eax, r12d
0x18002c5ad  mov     rcx, [rbp+40h+var_48]
0x18002c5b1  xor     rcx, rsp; StackCookie
0x18002c5b4  call    __security_check_cookie
0x18002c5b9  add     rsp, 108h
0x18002c5c0  pop     r15
0x18002c5c2  pop     r14
0x18002c5c4  pop     r13
0x18002c5c6  pop     r12
0x18002c5c8  pop     rdi
0x18002c5c9  pop     rsi
0x18002c5ca  pop     rbx
0x18002c5cb  pop     rbp
0x18002c5cc  retn
```
