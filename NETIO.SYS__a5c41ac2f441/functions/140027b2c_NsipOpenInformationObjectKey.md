# NsipOpenInformationObjectKey

- ea: `0x140027b2c`
- end: `0x140027dd7`
- name: `NsipOpenInformationObjectKey`
- size: `683`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140026fac`
- `0x14002764c`
- `0x140027810`

## callees

- `0x140027b2c`
- `0x140027de0`
- `0x140027e70`
- `0x140050ea4`
- `0x14005fe98`
- `0x1400605c8`
- `0x140077fa0`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x140027c5e`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140027c5e`
- `ntoskrnl!RtlStringFromGUID` at `0x140027bbe`
- `ntoskrnl!RtlStringFromGUID` at `0x140027bbe`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140027bff`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140027bff`

## string_xrefs

- `0x140027be1`: `\Registry\Machine\System\CurrentControlSet\Control\Nsi`

## pseudocode

```c
__int64 __fastcall NsipOpenInformationObjectKey(PHANDLE KeyHandle, unsigned int *a2, ACCESS_MASK a3)
{
  _BYTE *v6; // rcx
  __int64 v7; // r9
  NTSTATUS PersistedStateLocation; // ebx
  int v9; // r8d
  __int64 result; // rax
  __int64 v11; // [rsp+20h] [rbp-E0h]
  unsigned int v12; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v14[22]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v16[256]; // [rsp+70h] [rbp-90h] BYREF

  GuidString = 0;
  memset(v16, 0, sizeof(v16));
  memset(v14, 0, sizeof(v14));
  v12 = 0;
  if ( !*a2 && !*((_QWORD *)a2 + 1) )
    return 3221225485LL;
  v6 = (_BYTE *)*((_QWORD *)a2 + 1);
  if ( !v6 )
  {
    result = NsipFindModuleGuidByModuleId(*a2, v14);
    if ( (int)result < 0 )
      return result;
    v6 = v14;
  }
  v7 = *((unsigned int *)v6 + 1);
  if ( (_DWORD)v7 == 1 )
  {
    PersistedStateLocation = RtlStringFromGUID((const GUID *const)(v6 + 8), &GuidString);
    if ( PersistedStateLocation < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          20,
          WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids,
          (unsigned int)PersistedStateLocation);
      }
    }
    else
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"NsiPersistentStore",
                                 0,
                                 L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Nsi",
                                 0,
                                 v16,
                                 512,
                                 &v12);
      if ( PersistedStateLocation < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            21,
            WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids,
            (unsigned int)PersistedStateLocation);
        }
      }
      else
      {
        LODWORD(v11) = a2[4];
        if ( StringCbPrintfW(&v16[((unsigned __int64)v12 >> 1) - 1], 512LL - v12, L"\\%ls\\%u", GuidString.Buffer, v11) < 0 )
        {
          PersistedStateLocation = -1073741789;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
          {
            WPP_SF_SDD(WPP_GLOBAL_Control->AttachedDevice, 22, v9, GuidString.Buffer, a2[4]);
          }
        }
        else
        {
          PersistedStateLocation = NsipOpenKey(KeyHandle, v16, a3);
        }
      }
      RtlFreeUnicodeString(&GuidString);
    }
    return (unsigned int)PersistedStateLocation;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids, v7);
    }
    return 3221225659LL;
  }
}

```

## disassembly

```asm
0x140027b2c  mov     [rsp-8+arg_18], rbx
0x140027b31  push    rbp
0x140027b32  push    rsi
0x140027b33  push    rdi
0x140027b34  push    r14
0x140027b36  push    r15
0x140027b38  lea     rbp, [rsp-180h]
0x140027b40  sub     rsp, 280h
0x140027b47  mov     rax, cs:__security_cookie
0x140027b4e  xor     rax, rsp
0x140027b51  mov     [rbp+1A0h+var_30], rax
0x140027b58  mov     r15d, r8d
0x140027b5b  mov     rsi, rdx
0x140027b5e  mov     r14, rcx
0x140027b61  xorps   xmm0, xmm0
0x140027b64  mov     edi, 200h
0x140027b69  lea     rcx, [rsp+2A0h+var_230]; void *
0x140027b6e  mov     r8d, edi; Size
0x140027b71  xor     edx, edx; Val
0x140027b73  movups  xmmword ptr [rsp+2A0h+GuidString.Length], xmm0
0x140027b78  call    memset
0x140027b7d  xor     eax, eax
0x140027b7f  xorps   xmm0, xmm0
0x140027b82  movups  xmmword ptr [rsp+2A0h+var_248], xmm0
0x140027b87  mov     qword ptr [rsp+2A0h+var_248+0Eh], rax
0x140027b8c  mov     [rsp+2A0h+var_260], eax
0x140027b90  mov     eax, [rsi]
0x140027b92  test    eax, eax
0x140027b94  jz      loc_140027C93
0x140027b9a  mov     rcx, [rsi+8]
0x140027b9e  test    rcx, rcx
0x140027ba1  jz      loc_140027CFC
0x140027ba7  mov     r9d, [rcx+4]
0x140027bab  cmp     r9d, 1
0x140027baf  jnz     loc_140027CDF
0x140027bb5  add     rcx, 8; Guid
0x140027bb9  lea     rdx, [rsp+2A0h+GuidString]; GuidString
0x140027bbe  call    cs:__imp_RtlStringFromGUID
0x140027bc5  nop     dword ptr [rax+rax+00h]
0x140027bca  mov     ebx, eax
0x140027bcc  test    eax, eax
0x140027bce  js      loc_140027CA5
0x140027bd4  lea     rax, [rsp+2A0h+var_260]
0x140027bd9  xor     r9d, r9d
0x140027bdc  mov     [rsp+2A0h+var_270], rax
0x140027be1  lea     r8, NsiDefaultPersistentStoreRootKey; "\\Registry\\Machine\\System\\CurrentCon"...
0x140027be8  lea     rax, [rsp+2A0h+var_230]
0x140027bed  mov     [rsp+2A0h+var_278], edi
0x140027bf1  xor     edx, edx
0x140027bf3  mov     [rsp+2A0h+var_280], rax
0x140027bf8  lea     rcx, aNsipersistents; "NsiPersistentStore"
0x140027bff  call    cs:__imp_RtlGetPersistedStateLocation
0x140027c06  nop     dword ptr [rax+rax+00h]
0x140027c0b  mov     ebx, eax
0x140027c0d  test    eax, eax
0x140027c0f  js      loc_140027D3E
0x140027c15  mov     eax, [rsp+2A0h+var_260]
0x140027c19  lea     r8, aLsU; "\\%ls\\%u"
0x140027c20  mov     r9, [rsp+2A0h+GuidString.Buffer]
0x140027c25  sub     rdi, rax
0x140027c28  shr     rax, 1
0x140027c2b  mov     rdx, rdi; cbDest
0x140027c2e  lea     rcx, [rsp+rax*2+2A0h+pszDest]; pszDest
0x140027c33  mov     eax, [rsi+10h]
0x140027c36  mov     dword ptr [rsp+2A0h+var_280], eax
0x140027c3a  call    StringCbPrintfW
0x140027c3f  test    eax, eax
0x140027c41  js      loc_140027D87
0x140027c47  mov     r8d, r15d
0x140027c4a  lea     rdx, [rsp+2A0h+var_230]
0x140027c4f  mov     rcx, r14; KeyHandle
0x140027c52  call    NsipOpenKey
0x140027c57  mov     ebx, eax
0x140027c59  lea     rcx, [rsp+2A0h+GuidString]; UnicodeString
0x140027c5e  call    cs:__imp_RtlFreeUnicodeString
0x140027c65  nop     dword ptr [rax+rax+00h]
0x140027c6a  mov     eax, ebx
0x140027c6c  mov     rcx, [rbp+1A0h+var_30]
0x140027c73  xor     rcx, rsp; StackCookie
0x140027c76  call    __security_check_cookie
0x140027c7b  mov     rbx, [rsp+2A0h+arg_18]
0x140027c83  add     rsp, 280h
0x140027c8a  pop     r15
0x140027c8c  pop     r14
0x140027c8e  pop     rdi
0x140027c8f  pop     rsi
0x140027c90  pop     rbp
0x140027c91  retn
0x140027c93  cmp     qword ptr [rsi+8], 0
0x140027c98  jnz     loc_140027B9A
0x140027c9e  mov     eax, 0C000000Dh
0x140027ca3  jmp     short loc_140027C6C
0x140027ca5  mov     rcx, cs:WPP_GLOBAL_Control
0x140027cac  lea     rax, WPP_GLOBAL_Control
0x140027cb3  cmp     rcx, rax
0x140027cb6  jz      short loc_140027C6A
0x140027cb8  cmp     byte ptr [rcx+29h], 2
0x140027cbc  jb      short loc_140027C6A
0x140027cbe  mov     eax, [rcx+2Ch]
0x140027cc1  test    al, 10h
0x140027cc3  jz      short loc_140027C6A
0x140027cc5  mov     rcx, [rcx+18h]
0x140027cc9  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x140027cd0  mov     edx, 14h
0x140027cd5  mov     r9d, ebx
0x140027cd8  call    WPP_SF_d
0x140027cdd  jmp     short loc_140027C6A
0x140027cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140027ce6  lea     rax, WPP_GLOBAL_Control
0x140027ced  cmp     rcx, rax
0x140027cf0  jnz     short loc_140027D1A
0x140027cf2  mov     eax, 0C00000BBh
0x140027cf7  jmp     loc_140027C6C
0x140027cfc  lea     rdx, [rsp+2A0h+var_248]
0x140027d01  mov     ecx, eax
0x140027d03  call    NsipFindModuleGuidByModuleId
0x140027d08  test    eax, eax
0x140027d0a  js      loc_140027C6C
0x140027d10  lea     rcx, [rsp+2A0h+var_248]
0x140027d15  jmp     loc_140027BA7
0x140027d1a  cmp     byte ptr [rcx+29h], 2
0x140027d1e  jb      short loc_140027CF2
0x140027d20  mov     eax, [rcx+2Ch]
0x140027d23  test    al, 10h
0x140027d25  jz      short loc_140027CF2
0x140027d27  mov     rcx, [rcx+18h]
0x140027d2b  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x140027d32  mov     edx, 13h
0x140027d37  call    WPP_SF_d
0x140027d3c  jmp     short loc_140027CF2
0x140027d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d45  lea     rax, WPP_GLOBAL_Control
0x140027d4c  cmp     rcx, rax
0x140027d4f  jz      loc_140027C59
0x140027d55  cmp     byte ptr [rcx+29h], 2
0x140027d59  jb      loc_140027C59
0x140027d5f  mov     eax, [rcx+2Ch]
0x140027d62  test    al, 10h
0x140027d64  jz      loc_140027C59
0x140027d6a  mov     rcx, [rcx+18h]
0x140027d6e  lea     r8, WPP_d5c76eba730233b98a5ea3d25d1e0dd0_Traceguids
0x140027d75  mov     edx, 15h
0x140027d7a  mov     r9d, ebx
0x140027d7d  call    WPP_SF_d
0x140027d82  jmp     loc_140027C59
0x140027d87  mov     ebx, 0C0000023h
0x140027d8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140027d93  lea     rax, WPP_GLOBAL_Control
0x140027d9a  cmp     rcx, rax
0x140027d9d  jz      loc_140027C59
0x140027da3  cmp     byte ptr [rcx+29h], 2
0x140027da7  jb      loc_140027C59
0x140027dad  mov     eax, [rcx+2Ch]
0x140027db0  test    al, 10h
0x140027db2  jz      loc_140027C59
0x140027db8  mov     eax, [rsi+10h]
0x140027dbb  mov     edx, 16h
0x140027dc0  mov     r9, [rsp+2A0h+GuidString.Buffer]
0x140027dc5  mov     rcx, [rcx+18h]
0x140027dc9  mov     dword ptr [rsp+2A0h+var_280], eax
0x140027dcd  call    WPP_SF_SDD
0x140027dd2  jmp     loc_140027C59
```
