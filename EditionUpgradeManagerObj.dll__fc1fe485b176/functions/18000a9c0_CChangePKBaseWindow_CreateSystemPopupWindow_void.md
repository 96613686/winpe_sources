# CChangePKBaseWindow::CreateSystemPopupWindow(void)

- ea: `0x18000a9c0`
- end: `0x18000aa7b`
- name: `?CreateSystemPopupWindow@CChangePKBaseWindow@@UEAAJXZ`
- size: `187`
- prototype: `__int64 __fastcall(CChangePKBaseWindow *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000a9c0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a9f3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a9f3`

## pseudocode

```c
__int64 __fastcall CChangePKBaseWindow::CreateSystemPopupWindow(CChangePKBaseWindow *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  LPVOID v4; // rcx
  LPVOID v6; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  v2 = CoCreateInstance(&CLSID_PopupWindowFactory, 0, 1u, &GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1, &v6);
  v3 = v2;
  if ( v2 < 0
    || !*((_QWORD *)this + 1)
    && (v2 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v6 + 24LL))(v6, 8), v3 = v2, v2 < 0)
    || (v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, char *))(*(_QWORD *)v6 + 72LL))(
               v6,
               *((_QWORD *)this + 1),
               (char *)this + 16),
        v3 = v2,
        v2 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v2);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  v4 = v6;
  if ( v6 )
  {
    v6 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a9c0  mov     r11, rsp
0x18000a9c3  mov     [r11+8], rbx
0x18000a9c7  push    rdi
0x18000a9c8  sub     rsp, 30h
0x18000a9cc  xor     edx, edx; pUnkOuter
0x18000a9ce  mov     qword ptr [r11+10h], 0
0x18000a9d6  mov     rdi, rcx
0x18000a9d9  lea     rax, [r11+10h]
0x18000a9dd  lea     r9, _GUID_6a0017fe_df25_46eb_8a96_38df889cb5b1; riid
0x18000a9e4  mov     [r11-18h], rax
0x18000a9e8  lea     rcx, CLSID_PopupWindowFactory; rclsid
0x18000a9ef  lea     r8d, [rdx+1]; dwClsContext
0x18000a9f3  call    cs:__imp_CoCreateInstance
0x18000a9f9  mov     ebx, eax
0x18000a9fb  test    eax, eax
0x18000a9fd  js      short loc_18000AA41
0x18000a9ff  cmp     qword ptr [rdi+8], 0
0x18000aa04  jnz     short loc_18000AA22
0x18000aa06  mov     rcx, [rsp+38h+arg_8]
0x18000aa0b  mov     edx, 8
0x18000aa10  mov     rax, [rcx]
0x18000aa13  mov     rax, [rax+18h]
0x18000aa17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa1c  mov     ebx, eax
0x18000aa1e  test    eax, eax
0x18000aa20  js      short loc_18000AA41
0x18000aa22  mov     rcx, [rsp+38h+arg_8]
0x18000aa27  lea     r8, [rdi+10h]
0x18000aa2b  mov     rdx, [rdi+8]
0x18000aa2f  mov     rax, [rcx]
0x18000aa32  mov     rax, [rax+48h]
0x18000aa36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa3b  mov     ebx, eax
0x18000aa3d  test    eax, eax
0x18000aa3f  jns     short loc_18000AA48
0x18000aa41  mov     ecx, eax
0x18000aa43  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000aa48  mov     ecx, ebx
0x18000aa4a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000aa4f  mov     rcx, [rsp+38h+arg_8]
0x18000aa54  test    rcx, rcx
0x18000aa57  jz      short loc_18000AA6E
0x18000aa59  mov     [rsp+38h+arg_8], 0
0x18000aa62  mov     rax, [rcx]
0x18000aa65  mov     rax, [rax+10h]
0x18000aa69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa6e  mov     eax, ebx
0x18000aa70  mov     rbx, [rsp+38h+arg_0]
0x18000aa75  add     rsp, 30h
0x18000aa79  pop     rdi
0x18000aa7a  retn
```
