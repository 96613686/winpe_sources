# wWinMain

- ea: `0x140003eb4`
- end: `0x140003f9d`
- name: `wWinMain`
- size: `233`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400012c0`

## callees

- `0x140001fac`
- `0x14000369c`
- `0x140003eb4`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x140003eeb`
- `KERNEL32!InitOnceExecuteOnce` at `0x140003eeb`
- `KERNEL32!GetCurrentThreadId` at `0x140003ecf`
- `KERNEL32!GetCurrentThreadId` at `0x140003ecf`
- `USER32!GetMessageW` at `0x140003f79`
- `USER32!GetMessageW` at `0x140003f79`
- `USER32!DispatchMessageW` at `0x140003f66`
- `USER32!DispatchMessageW` at `0x140003f66`
- `USER32!TranslateMessage` at `0x140003f5b`
- `USER32!TranslateMessage` at `0x140003f5b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003f8f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140003f8f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003ec1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140003ec1`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  DWORD CurrentThreadId; // ebx
  MSG Msg; // [rsp+20h] [rbp-38h] BYREF

  if ( CoInitializeEx(0, 2u) >= 0 )
  {
    CurrentThreadId = GetCurrentThreadId();
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<CSingleUseOutOfProcModule>::initOnceOutOfProc_,
      _lambda_f1e7f17610f55d1f3f4cf582571324a1_::_lambda_invoker_cdecl_,
      0,
      0);
    byte_14000C880 = 1;
    if ( !qword_14000C878 )
    {
      byte_14000C8A8 = 1;
      qword_14000C890 = (__int64)off_1400090B0;
      qword_14000C878 = (__int64)&qword_14000C890;
      byte_14000C898 = 0;
      dword_14000C8A0 = CurrentThreadId;
    }
    if ( (int)Microsoft::WRL::Details::RegisterObjects<2>(&Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int>::instance_) >= 0 )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterObjects((Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int>::instance_);
    }
    CoUninitialize();
  }
  return 0;
}

```

## disassembly

```asm
0x140003eb4  push    rbx
0x140003eb6  sub     rsp, 50h
0x140003eba  mov     edx, 2; dwCoInit
0x140003ebf  xor     ecx, ecx; pvReserved
0x140003ec1  call    cs:__imp_CoInitializeEx
0x140003ec7  test    eax, eax
0x140003ec9  js      loc_140003F95
0x140003ecf  call    cs:__imp_GetCurrentThreadId
0x140003ed5  xor     r9d, r9d; Context
0x140003ed8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f1e7f17610f55d1f3f4cf582571324a1_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x140003edf  xor     r8d, r8d; Parameter
0x140003ee2  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VCSingleUseOutOfProcModule@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x140003ee9  mov     ebx, eax
0x140003eeb  call    cs:__imp_InitOnceExecuteOnce
0x140003ef1  cmp     cs:qword_14000C878, 0
0x140003ef9  mov     cs:byte_14000C880, 1
0x140003f00  jnz     short loc_140003F32
0x140003f02  lea     rax, off_1400090B0
0x140003f09  mov     cs:byte_14000C8A8, 1
0x140003f10  mov     cs:qword_14000C890, rax
0x140003f17  lea     rax, qword_14000C890
0x140003f1e  mov     cs:qword_14000C878, rax
0x140003f25  mov     cs:byte_14000C898, 0
0x140003f2c  mov     cs:dword_14000C8A0, ebx
0x140003f32  lea     rcx, ?instance_@?$StaticStorage@VCSingleUseOutOfProcModule@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int> Microsoft::WRL::Details::StaticStorage<CSingleUseOutOfProcModule,1,int>::instance_
0x140003f39  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x140003f3e  test    eax, eax
0x140003f40  js      short loc_140003F8F
0x140003f42  xorps   xmm0, xmm0
0x140003f45  movups  xmmword ptr [rsp+58h+Msg.hwnd], xmm0
0x140003f4a  movups  xmmword ptr [rsp+58h+Msg.wParam], xmm0
0x140003f4f  movups  xmmword ptr [rsp+58h+Msg.time], xmm0
0x140003f54  jmp     short loc_140003F6C
0x140003f56  lea     rcx, [rsp+58h+Msg]; lpMsg
0x140003f5b  call    cs:__imp_TranslateMessage
0x140003f61  lea     rcx, [rsp+58h+Msg]; lpMsg
0x140003f66  call    cs:__imp_DispatchMessageW
0x140003f6c  xor     r9d, r9d; wMsgFilterMax
0x140003f6f  lea     rcx, [rsp+58h+Msg]; lpMsg
0x140003f74  xor     r8d, r8d; wMsgFilterMin
0x140003f77  xor     edx, edx; hWnd
0x140003f79  call    cs:__imp_GetMessageW
0x140003f7f  test    eax, eax
0x140003f81  jg      short loc_140003F56
0x140003f83  lea     rcx, ?instance_@?$StaticStorage@VCSingleUseOutOfProcModule@@$00H@Details@WRL@Microsoft@@0V1234@A; this
0x140003f8a  call    ?UnregisterObjects@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@QEAAJPEBG@Z; Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterObjects(ushort const *)
0x140003f8f  call    cs:__imp_CoUninitialize
0x140003f95  xor     eax, eax
0x140003f97  add     rsp, 50h
0x140003f9b  pop     rbx
0x140003f9c  retn
```
