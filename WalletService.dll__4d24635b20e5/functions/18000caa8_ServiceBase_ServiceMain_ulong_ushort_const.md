# ServiceBase::ServiceMain(ulong,ushort const * *)

- ea: `0x18000caa8`
- end: `0x18000cb9b`
- name: `?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z`
- size: `243`
- prototype: `__int64 __fastcall(ServiceBase *this, __int64, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c050`

## callees

- `0x18000ac74`
- `0x18000c958`
- `0x18000ca04`
- `0x18000caa8`
- `0x18000ce8c`
- `0x18000cf58`
- `0x18000d450`
- `0x18000d4f4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000cae7`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000cae7`

## pseudocode

```c
__int64 __fastcall ServiceBase::ServiceMain(ServiceBase *this, __int64 a2, const unsigned __int16 **a3)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  ServiceBase *v11; // [rsp+20h] [rbp-18h] BYREF
  char v12; // [rsp+28h] [rbp-10h]
  ServiceBase *v13; // [rsp+40h] [rbp+8h] BYREF

  v13 = this;
  ServiceBase::_ServiceInit(this);
  StringCchCopyW(&ServiceName, 0x20u, *a3);
  qword_18006C058 = (__int64)RegisterServiceCtrlHandlerExW(&ServiceName, ServiceBase::_ServiceCtrlHandler, &g_rwService);
  if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v4, ServiceBaseServiceStarting, &ServiceName);
  v12 = 1;
  v11 = *(ServiceBase **)lambda_76157c6db852dcd9bfc939eeb59d0b61_::_lambda_76157c6db852dcd9bfc939eeb59d0b61_(&v13);
  v5 = ServiceBase::_ServiceMainInner(v11);
  v8 = v5;
  if ( v5 >= 0 )
  {
    if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(v7, ServiceBaseServiceStarted, &ServiceName);
    v12 = 0;
    v8 = 0;
  }
  else
  {
    v9 = v5 & 0x1FFF0000;
    if ( (_DWORD)v9 == 458752 )
    {
      dword_18006C07C = (unsigned __int16)v5;
    }
    else
    {
      if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 1) != 0 )
        McTemplateU0qz_EventWriteTransfer(v9, v6, (unsigned int)v5, &ServiceName);
      dword_18006C07C = v8;
    }
  }
  tlx::_UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61___::__UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61___(&v11);
  return v8;
}

```

## disassembly

```asm
0x18000caa8  mov     [rsp+arg_8], rbx
0x18000caad  mov     [rsp+arg_0], rcx
0x18000cab2  push    rdi
0x18000cab3  sub     rsp, 30h
0x18000cab7  mov     rbx, r8
0x18000caba  call    ?_ServiceInit@ServiceBase@@AEAAXXZ; ServiceBase::_ServiceInit(void)
0x18000cabf  mov     r8, [rbx]; unsigned __int16 *
0x18000cac2  lea     rdi, ServiceName
0x18000cac9  mov     rcx, rdi; unsigned __int16 *
0x18000cacc  mov     edx, 20h ; ' '; unsigned __int64
0x18000cad1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000cad6  lea     r8, ?g_rwService@@3VRWService@@A; lpContext
0x18000cadd  mov     rcx, rdi; lpServiceName
0x18000cae0  lea     rdx, ?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z; lpHandlerProc
0x18000cae7  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000caed  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 8
0x18000caf4  mov     cs:qword_18006C058, rax
0x18000cafb  jz      short loc_18000CB0C
0x18000cafd  mov     r8, rdi
0x18000cb00  lea     rdx, ServiceBaseServiceStarting
0x18000cb07  call    McTemplateU0z_EventWriteTransfer
0x18000cb0c  lea     rcx, [rsp+38h+arg_0]
0x18000cb11  call    _lambda_76157c6db852dcd9bfc939eeb59d0b61____lambda_76157c6db852dcd9bfc939eeb59d0b61_
0x18000cb16  mov     [rsp+38h+var_10], 1
0x18000cb1b  mov     rcx, [rax]; this
0x18000cb1e  mov     [rsp+38h+var_18], rcx
0x18000cb23  call    ?_ServiceMainInner@ServiceBase@@AEAAJXZ; ServiceBase::_ServiceMainInner(void)
0x18000cb28  mov     ebx, eax
0x18000cb2a  test    eax, eax
0x18000cb2c  jns     short loc_18000CB65
0x18000cb2e  mov     ecx, eax
0x18000cb30  and     ecx, 1FFF0000h
0x18000cb36  cmp     ecx, 70000h
0x18000cb3c  jnz     short loc_18000CB49
0x18000cb3e  movzx   ecx, bx
0x18000cb41  mov     cs:dword_18006C07C, ecx
0x18000cb47  jmp     short loc_18000CB84
0x18000cb49  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 1
0x18000cb50  jz      short loc_18000CB5D
0x18000cb52  mov     r9, rdi
0x18000cb55  mov     r8d, ebx
0x18000cb58  call    McTemplateU0qz_EventWriteTransfer
0x18000cb5d  mov     cs:dword_18006C07C, ebx
0x18000cb63  jmp     short loc_18000CB84
0x18000cb65  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 10h
0x18000cb6c  jz      short loc_18000CB7D
0x18000cb6e  mov     r8, rdi
0x18000cb71  lea     rdx, ServiceBaseServiceStarted
0x18000cb78  call    McTemplateU0z_EventWriteTransfer
0x18000cb7d  mov     [rsp+38h+var_10], 0
0x18000cb82  xor     ebx, ebx
0x18000cb84  lea     rcx, [rsp+38h+var_18]
0x18000cb89  call    tlx___UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61_______UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61___
0x18000cb8e  mov     eax, ebx
0x18000cb90  mov     rbx, [rsp+38h+arg_8]
0x18000cb95  add     rsp, 30h
0x18000cb99  pop     rdi
0x18000cb9a  retn
```
