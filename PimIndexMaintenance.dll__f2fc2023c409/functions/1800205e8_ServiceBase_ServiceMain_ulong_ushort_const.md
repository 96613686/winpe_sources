# ServiceBase::ServiceMain(ulong,ushort const * *)

- ea: `0x1800205e8`
- end: `0x180020719`
- name: `?ServiceMain@ServiceBase@@QEAAJKPEAPEBG@Z`
- size: `305`
- prototype: `__int64 __fastcall(ServiceBase *__hidden this, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d0d0`

## callees

- `0x18002049c`
- `0x180020548`
- `0x1800205e8`
- `0x1800209ec`
- `0x180020ab8`
- `0x180020e00`
- `0x180020ea4`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180020660`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180020660`

## pseudocode

```c
__int64 __fastcall ServiceBase::ServiceMain(ServiceBase *this, __int64 a2, WCHAR **a3)
{
  WCHAR *v4; // r8
  WCHAR *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  __int64 v9; // rcx
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  unsigned int v13; // ebx
  __int64 v14; // rcx
  ServiceBase *v16; // [rsp+20h] [rbp-18h] BYREF
  char v17; // [rsp+28h] [rbp-10h]
  ServiceBase *v18; // [rsp+40h] [rbp+8h] BYREF

  v18 = this;
  ServiceBase::_ServiceInit(this);
  v4 = *a3;
  v5 = &ServiceName;
  v6 = 2147483646;
  v7 = 32;
  do
  {
    if ( !v6 )
      break;
    if ( !*v4 )
      break;
    *v5++ = *v4++;
    --v6;
    --v7;
  }
  while ( v7 );
  v8 = v5 - 1;
  if ( v7 )
    v8 = v5;
  *v8 = 0;
  qword_18002DCA8 = (__int64)RegisterServiceCtrlHandlerExW(
                               &ServiceName,
                               (LPHANDLER_FUNCTION_EX)ServiceBase::_ServiceCtrlHandler,
                               &myService);
  if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 8) != 0 )
    McTemplateU0z_EventWriteTransfer(v9, ServiceBaseServiceStarting, &ServiceName);
  v17 = 1;
  v16 = *(ServiceBase **)lambda_76157c6db852dcd9bfc939eeb59d0b61_::_lambda_76157c6db852dcd9bfc939eeb59d0b61_(&v18);
  v10 = ServiceBase::_ServiceMainInner(v16);
  v13 = v10;
  if ( v10 >= 0 )
  {
    if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(v12, ServiceBaseServiceStarted, &ServiceName);
    v17 = 0;
    v13 = 0;
  }
  else
  {
    v14 = v10 & 0x1FFF0000;
    if ( (_DWORD)v14 == 458752 )
    {
      dword_18002DCCC = (unsigned __int16)v10;
    }
    else
    {
      if ( (Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits & 1) != 0 )
        McTemplateU0qz_EventWriteTransfer(v14, v11, (unsigned int)v10, &ServiceName);
      dword_18002DCCC = v13;
    }
  }
  tlx::_UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61___::__UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61___(&v16);
  return v13;
}

```

## disassembly

```asm
0x1800205e8  mov     [rsp+arg_8], rbx
0x1800205ed  mov     [rsp+arg_10], rsi
0x1800205f2  mov     [rsp+arg_0], rcx
0x1800205f7  push    rdi
0x1800205f8  sub     rsp, 30h
0x1800205fc  mov     rbx, r8
0x1800205ff  call    ?_ServiceInit@ServiceBase@@AEAAXXZ; ServiceBase::_ServiceInit(void)
0x180020604  mov     r8, [rbx]
0x180020607  lea     rsi, ServiceName
0x18002060e  mov     rax, rsi
0x180020611  mov     ecx, 7FFFFFFEh
0x180020616  mov     edx, 20h ; ' '
0x18002061b  xor     edi, edi
0x18002061d  test    rcx, rcx
0x180020620  jz      short loc_180020641
0x180020622  movzx   r9d, word ptr [r8]
0x180020626  test    r9w, r9w
0x18002062a  jz      short loc_180020641
0x18002062c  mov     [rax], r9w
0x180020630  add     r8, 2
0x180020634  add     rax, 2
0x180020638  dec     rcx
0x18002063b  sub     rdx, 1
0x18002063f  jnz     short loc_18002061D
0x180020641  test    rdx, rdx
0x180020644  lea     rcx, [rax-2]
0x180020648  lea     r8, ?myService@@3VPimIMService@@A; lpContext
0x18002064f  cmovnz  rcx, rax
0x180020653  lea     rdx, ?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z; lpHandlerProc
0x18002065a  mov     [rcx], di
0x18002065d  mov     rcx, rsi; lpServiceName
0x180020660  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180020666  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 8
0x18002066d  mov     cs:qword_18002DCA8, rax
0x180020674  jz      short loc_180020685
0x180020676  mov     r8, rsi
0x180020679  lea     rdx, ServiceBaseServiceStarting
0x180020680  call    McTemplateU0z_EventWriteTransfer
0x180020685  lea     rcx, [rsp+38h+arg_0]
0x18002068a  call    _lambda_76157c6db852dcd9bfc939eeb59d0b61____lambda_76157c6db852dcd9bfc939eeb59d0b61_
0x18002068f  mov     [rsp+38h+var_10], 1
0x180020694  mov     rcx, [rax]; this
0x180020697  mov     [rsp+38h+var_18], rcx
0x18002069c  call    ?_ServiceMainInner@ServiceBase@@AEAAJXZ; ServiceBase::_ServiceMainInner(void)
0x1800206a1  mov     ebx, eax
0x1800206a3  test    eax, eax
0x1800206a5  jns     short loc_1800206DE
0x1800206a7  mov     ecx, eax
0x1800206a9  and     ecx, 1FFF0000h
0x1800206af  cmp     ecx, 70000h
0x1800206b5  jnz     short loc_1800206C2
0x1800206b7  movzx   ecx, bx
0x1800206ba  mov     cs:dword_18002DCCC, ecx
0x1800206c0  jmp     short loc_1800206FD
0x1800206c2  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 1
0x1800206c9  jz      short loc_1800206D6
0x1800206cb  mov     r9, rsi
0x1800206ce  mov     r8d, ebx
0x1800206d1  call    McTemplateU0qz_EventWriteTransfer
0x1800206d6  mov     cs:dword_18002DCCC, ebx
0x1800206dc  jmp     short loc_1800206FD
0x1800206de  test    cs:Microsoft_Windows_UserDataAccess_UserDataUtilsEnableBits, 10h
0x1800206e5  jz      short loc_1800206F6
0x1800206e7  mov     r8, rsi
0x1800206ea  lea     rdx, ServiceBaseServiceStarted
0x1800206f1  call    McTemplateU0z_EventWriteTransfer
0x1800206f6  mov     [rsp+38h+var_10], dil
0x1800206fb  mov     ebx, edi
0x1800206fd  lea     rcx, [rsp+38h+var_18]
0x180020702  call    tlx___UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61_______UndoSolo__lambda_76157c6db852dcd9bfc939eeb59d0b61___
0x180020707  mov     rsi, [rsp+38h+arg_10]
0x18002070c  mov     eax, ebx
0x18002070e  mov     rbx, [rsp+38h+arg_8]
0x180020713  add     rsp, 30h
0x180020717  pop     rdi
0x180020718  retn
```
