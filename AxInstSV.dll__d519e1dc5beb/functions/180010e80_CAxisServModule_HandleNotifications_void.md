# CAxisServModule::_HandleNotifications(void *)

- ea: `0x180010e80`
- end: `0x180010edc`
- name: `?_HandleNotifications@CAxisServModule@@SAIPEAX@Z`
- size: `92`
- prototype: `unsigned int __fastcall(CAxisServModule *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000725c`
- `0x18000bbfc`
- `0x180010e80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180010ece`
- `api-ms-win-crt-private-l1-1-0!_o__endthreadex` at `0x180010ece`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010e90`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010e90`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010ec6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010ec6`

## pseudocode

```c
__int64 __fastcall CAxisServModule::_HandleNotifications(CAxisServModule *this)
{
  int v2; // eax
  int v4; // [rsp+20h] [rbp-18h]

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    v2 = CAxisServModule::HandleGPNotifications(this);
    if ( v2 < 0 )
    {
      v4 = v2;
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 2u, L"Error handling GP Notification 0x%x", v4);
    }
    CoUninitialize();
  }
  _o__endthreadex(0);
  return 0;
}

```

## disassembly

```asm
0x180010e80  push    rbx
0x180010e82  sub     rsp, 30h
0x180010e86  mov     rbx, rcx
0x180010e89  mov     edx, 2; dwCoInit
0x180010e8e  xor     ecx, ecx; pvReserved
0x180010e90  call    cs:__imp_CoInitializeEx
0x180010e96  test    eax, eax
0x180010e98  js      short loc_180010ECC
0x180010e9a  mov     rcx, rbx; this
0x180010e9d  call    ?HandleGPNotifications@CAxisServModule@@QEAAJXZ; CAxisServModule::HandleGPNotifications(void)
0x180010ea2  test    eax, eax
0x180010ea4  jns     short loc_180010EC6
0x180010ea6  mov     edx, 8; unsigned int
0x180010eab  mov     [rsp+38h+var_18], eax
0x180010eaf  lea     r9, aErrorHandlingG; "Error handling GP Notification 0x%x"
0x180010eb6  lea     rcx, qword_180021AD8; this
0x180010ebd  lea     r8d, [rdx-6]; unsigned __int8
0x180010ec1  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180010ec6  call    cs:__imp_CoUninitialize
0x180010ecc  xor     ecx, ecx
0x180010ece  call    cs:__imp__o__endthreadex
0x180010ed4  xor     eax, eax
0x180010ed6  add     rsp, 30h
0x180010eda  pop     rbx
0x180010edb  retn
```
