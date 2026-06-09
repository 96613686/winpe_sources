# DestroySecurityAttributes

- ea: `0x140077ce4`
- end: `0x140077e48`
- name: `DestroySecurityAttributes`
- size: `356`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140076c74`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x14006998c`
- `0x140077ce4`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140077dc8`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140077dc8`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x140077d57`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x140077d57`
- `KERNEL32!GetLastError` at `0x140077d7f`
- `KERNEL32!GetLastError` at `0x140077df0`
- `KERNEL32!GetLastError` at `0x140077d7f`
- `KERNEL32!GetLastError` at `0x140077df0`
- `KERNEL32!LocalFree` at `0x140077e22`
- `KERNEL32!LocalFree` at `0x140077e22`

## pseudocode

```c
__int64 __fastcall DestroySecurityAttributes(_QWORD *lpMem)
{
  void *v2; // rbx
  DWORD LastError; // eax
  DWORD v4; // eax
  WINBOOL bOwnerDefaulted; // [rsp+40h] [rbp+8h] BYREF
  WINBOOL bDaclPresent; // [rsp+48h] [rbp+10h] BYREF
  PSID pOwner; // [rsp+50h] [rbp+18h] BYREF
  PACL pDacl; // [rsp+58h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  v2 = (void *)lpMem[1];
  bOwnerDefaulted = 0;
  bDaclPresent = 0;
  pOwner = 0;
  pDacl = 0;
  if ( GetSecurityDescriptorOwner(v2, &pOwner, &bOwnerDefaulted) )
  {
    pMemFree(pOwner);
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
  }
  if ( GetSecurityDescriptorDacl(v2, &bDaclPresent, &pDacl, &bOwnerDefaulted) )
  {
    LocalFree(pDacl);
  }
  else if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_db036311db36307996a98c23702218b2_Traceguids, v4);
  }
  pMemFree(lpMem);
  return pMemFree(v2);
}

```

## disassembly

```asm
0x140077ce4  push    rbx
0x140077ce6  push    rdi
0x140077ce7  push    r14
0x140077ce9  sub     rsp, 20h
0x140077ced  mov     rdi, rcx
0x140077cf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140077cf7  lea     r14, WPP_GLOBAL_Control
0x140077cfe  cmp     rcx, r14
0x140077d01  jz      short loc_140077D24
0x140077d03  test    byte ptr [rcx+1Ch], 2
0x140077d07  jz      short loc_140077D24
0x140077d09  cmp     byte ptr [rcx+19h], 5
0x140077d0d  jb      short loc_140077D24
0x140077d0f  mov     rcx, [rcx+10h]
0x140077d13  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077d1a  mov     edx, 43h ; 'C'
0x140077d1f  call    WPP_SF_
0x140077d24  mov     rbx, [rdi+8]
0x140077d28  lea     r8, [rsp+38h+bOwnerDefaulted]; lpbOwnerDefaulted
0x140077d2d  mov     rcx, rbx; pSecurityDescriptor
0x140077d30  mov     [rsp+38h+bOwnerDefaulted], 0
0x140077d38  lea     rdx, [rsp+38h+pOwner]; pOwner
0x140077d3d  mov     [rsp+38h+bDaclPresent], 0
0x140077d45  mov     [rsp+38h+pOwner], 0
0x140077d4e  mov     [rsp+38h+pDacl], 0
0x140077d57  call    cs:__imp_GetSecurityDescriptorOwner
0x140077d5e  nop     dword ptr [rax+rax+00h]
0x140077d63  test    eax, eax
0x140077d65  jnz     short loc_140077DAC
0x140077d67  mov     rax, cs:WPP_GLOBAL_Control
0x140077d6e  cmp     rax, r14
0x140077d71  jz      short loc_140077DB6
0x140077d73  test    byte ptr [rax+1Ch], 2
0x140077d77  jz      short loc_140077DB6
0x140077d79  cmp     byte ptr [rax+19h], 2
0x140077d7d  jb      short loc_140077DB6
0x140077d7f  call    cs:__imp_GetLastError
0x140077d86  nop     dword ptr [rax+rax+00h]
0x140077d8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140077d92  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077d99  mov     edx, 44h ; 'D'
0x140077d9e  mov     r9d, eax
0x140077da1  mov     rcx, [rcx+10h]
0x140077da5  call    WPP_SF_d
0x140077daa  jmp     short loc_140077DB6
0x140077dac  mov     rcx, [rsp+38h+pOwner]; lpMem
0x140077db1  call    pMemFree
0x140077db6  lea     r9, [rsp+38h+bOwnerDefaulted]; lpbDaclDefaulted
0x140077dbb  mov     rcx, rbx; pSecurityDescriptor
0x140077dbe  lea     r8, [rsp+38h+pDacl]; pDacl
0x140077dc3  lea     rdx, [rsp+38h+bDaclPresent]; lpbDaclPresent
0x140077dc8  call    cs:__imp_GetSecurityDescriptorDacl
0x140077dcf  nop     dword ptr [rax+rax+00h]
0x140077dd4  test    eax, eax
0x140077dd6  jnz     short loc_140077E1D
0x140077dd8  mov     rax, cs:WPP_GLOBAL_Control
0x140077ddf  cmp     rax, r14
0x140077de2  jz      short loc_140077E2E
0x140077de4  test    byte ptr [rax+1Ch], 2
0x140077de8  jz      short loc_140077E2E
0x140077dea  cmp     byte ptr [rax+19h], 2
0x140077dee  jb      short loc_140077E2E
0x140077df0  call    cs:__imp_GetLastError
0x140077df7  nop     dword ptr [rax+rax+00h]
0x140077dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140077e03  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140077e0a  mov     edx, 45h ; 'E'
0x140077e0f  mov     r9d, eax
0x140077e12  mov     rcx, [rcx+10h]
0x140077e16  call    WPP_SF_d
0x140077e1b  jmp     short loc_140077E2E
0x140077e1d  mov     rcx, [rsp+38h+pDacl]; hMem
0x140077e22  call    cs:__imp_LocalFree
0x140077e29  nop     dword ptr [rax+rax+00h]
0x140077e2e  mov     rcx, rdi; lpMem
0x140077e31  call    pMemFree
0x140077e36  mov     rcx, rbx; lpMem
0x140077e39  call    pMemFree
0x140077e3e  add     rsp, 20h
0x140077e42  pop     r14
0x140077e44  pop     rdi
0x140077e45  pop     rbx
0x140077e46  retn
```
