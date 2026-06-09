# CSyncChangeUnitWrapper::SetUpdateVersion(_SYNC_VERSION *)

- ea: `0x180072e8c`
- end: `0x180072f39`
- name: `?SetUpdateVersion@CSyncChangeUnitWrapper@@QEAAJPEAU_SYNC_VERSION@@@Z`
- size: `173`
- prototype: `__int64 __fastcall(CSyncChangeUnitWrapper *__hidden this, struct _SYNC_VERSION *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18006d858`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x180072e8c`

## string_xrefs

- `0x180072ebe`: `CSyncChangeUnitWrapper::SetUpdateVersion`
- `0x180072f12`: `CSyncChangeUnitWrapper::SetUpdateVersion`

## pseudocode

```c
__int64 __fastcall CSyncChangeUnitWrapper::SetUpdateVersion(CSyncChangeUnitWrapper *this, struct _SYNC_VERSION *a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids,
      "CSyncChangeUnitWrapper::SetUpdateVersion");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147467261;
  if ( a2 )
  {
    v5 = 0;
    *((_DWORD *)this + 8) = a2->dwLastUpdatingReplicaKey;
    *((_QWORD *)this + 5) = a2->ullTickCount;
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      57,
      (unsigned int)WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids,
      (unsigned int)"CSyncChangeUnitWrapper::SetUpdateVersion",
      v5);
  return v5;
}

```

## disassembly

```asm
0x180072e8c  push    rbx
0x180072e8e  push    rbp
0x180072e8f  push    rsi
0x180072e90  push    rdi
0x180072e91  sub     rsp, 38h
0x180072e95  mov     rdi, rdx
0x180072e98  mov     rsi, rcx
0x180072e9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180072ea2  lea     rbp, WPP_GLOBAL_Control
0x180072ea9  cmp     rcx, rbp
0x180072eac  jz      short loc_180072EDD
0x180072eae  test    byte ptr [rcx+1Ch], 8
0x180072eb2  jz      short loc_180072EDD
0x180072eb4  cmp     byte ptr [rcx+19h], 5
0x180072eb8  jb      short loc_180072EDD
0x180072eba  mov     rcx, [rcx+10h]
0x180072ebe  lea     r9, aCsyncchangeuni_12; "CSyncChangeUnitWrapper::SetUpdateVersio"...
0x180072ec5  mov     edx, 38h ; '8'
0x180072eca  lea     r8, WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids
0x180072ed1  call    WPP_SF_s
0x180072ed6  mov     rcx, cs:WPP_GLOBAL_Control
0x180072edd  mov     ebx, 80004003h
0x180072ee2  test    rdi, rdi
0x180072ee5  jz      short loc_180072EFD
0x180072ee7  mov     eax, [rdi]
0x180072ee9  xor     ebx, ebx
0x180072eeb  mov     [rsi+20h], eax
0x180072eee  mov     rax, [rdi+8]
0x180072ef2  mov     [rsi+28h], rax
0x180072ef6  mov     rcx, cs:WPP_GLOBAL_Control
0x180072efd  cmp     rcx, rbp
0x180072f00  jz      short loc_180072F2E
0x180072f02  test    byte ptr [rcx+1Ch], 8
0x180072f06  jz      short loc_180072F2E
0x180072f08  cmp     byte ptr [rcx+19h], 5
0x180072f0c  jb      short loc_180072F2E
0x180072f0e  mov     rcx, [rcx+10h]
0x180072f12  lea     r9, aCsyncchangeuni_12; "CSyncChangeUnitWrapper::SetUpdateVersio"...
0x180072f19  mov     edx, 39h ; '9'
0x180072f1e  mov     [rsp+58h+var_38], ebx
0x180072f22  lea     r8, WPP_e2efb66d97a1346b7c1308d867b5aff5_Traceguids
0x180072f29  call    WPP_SF_sD
0x180072f2e  mov     eax, ebx
0x180072f30  add     rsp, 38h
0x180072f34  pop     rdi
0x180072f35  pop     rsi
0x180072f36  pop     rbp
0x180072f37  pop     rbx
0x180072f38  retn
```
