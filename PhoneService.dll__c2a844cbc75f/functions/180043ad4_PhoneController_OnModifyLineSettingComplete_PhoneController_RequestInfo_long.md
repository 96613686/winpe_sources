# PhoneController::_OnModifyLineSettingComplete(PhoneController::RequestInfo *,long)

- ea: `0x180043ad4`
- end: `0x180043c4f`
- name: `?_OnModifyLineSettingComplete@PhoneController@@IEAAXPEAURequestInfo@1@J@Z`
- size: `379`
- prototype: `void __fastcall(PhoneController *__hidden this, struct PhoneController::RequestInfo *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043f90`

## callees

- `0x180005660`
- `0x18002c574`
- `0x18002c580`
- `0x180043ad4`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043aee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043b0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043aee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043b0e`

## string_xrefs

- `0x180043c0e`: `onecoreuap\net\phone\phoneservice\service\lib\ControllerMessagesPriv.h`
- `0x180043b02`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180043be8`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180043c2d`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
void __fastcall PhoneController::_OnModifyLineSettingComplete(
        PhoneController *this,
        struct PhoneController::RequestInfo *a2,
        int a3)
{
  __int64 v6; // rcx
  int v7; // esi
  __int128 v8; // xmm6
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  struct ATL::CAtlModule *v11; // rcx
  __int64 v12; // rcx
  int v13; // eax

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8431);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = *((_DWORD *)a2 + 7);
  v8 = *(_OWORD *)(*(_QWORD *)a2 + 88LL);
  v9 = operator new(0x40u);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0x40u);
    v11 = ATL::_pAtlModule;
    *(_QWORD *)v10 = &ATL::CComObject<SendLineSettingModifiedMessage>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v11 + 8LL))(v11);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 8LL))(v10);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 8LL))(v10);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
    v10[6] = 23;
    *((_OWORD *)v10 + 2) = v8;
    v12 = *((_QWORD *)v10 + 6);
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      *((_QWORD *)v10 + 6) = 0;
    }
    v10[14] = a3;
    v10[15] = v7;
    v13 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)this + 26) + 40LL))(*((_QWORD *)this + 26), v10);
    if ( v13 < 0 )
      Log_HREvent_7((unsigned int)v13, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8441);
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  else
  {
    Log_HREvent_7(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\ControllerMessagesPriv.h", 1333);
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 8445);
  }
}

```

## disassembly

```asm
0x180043ad4  mov     [rsp+arg_10], rbx
0x180043ad9  push    rbp
0x180043ada  push    rsi
0x180043adb  push    rdi
0x180043adc  sub     rsp, 40h
0x180043ae0  movaps  [rsp+58h+var_28], xmm6
0x180043ae5  mov     ebp, r8d
0x180043ae8  mov     rbx, rdx
0x180043aeb  mov     rdi, rcx
0x180043aee  call    cs:__imp_GetCurrentThreadId
0x180043af4  cmp     [rdi+0F0h], eax
0x180043afa  jz      short loc_180043B21
0x180043afc  mov     r8d, 20EFh
0x180043b02  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180043b09  call    Log_AssertionEvent_3
0x180043b0e  call    cs:__imp_GetCurrentThreadId
0x180043b14  cmp     [rdi+0F0h], eax
0x180043b1a  jz      short loc_180043B21
0x180043b1c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180043b21  mov     rax, [rbx]
0x180043b24  mov     ecx, 40h ; '@'; Size
0x180043b29  mov     esi, [rbx+1Ch]
0x180043b2c  movups  xmm6, xmmword ptr [rax+58h]
0x180043b30  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180043b35  mov     rbx, rax
0x180043b38  test    rax, rax
0x180043b3b  jz      loc_180043C09
0x180043b41  xor     edx, edx; Val
0x180043b43  mov     rcx, rax; void *
0x180043b46  lea     r8d, [rdx+40h]; Size
0x180043b4a  call    memset_0
0x180043b4f  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180043b56  lea     rax, ??_7?$CComObject@VSendLineSettingModifiedMessage@@@ATL@@6B@; const ATL::CComObject<SendLineSettingModifiedMessage>::`vftable'
0x180043b5d  mov     [rbx], rax
0x180043b60  mov     rax, [rcx]
0x180043b63  mov     rax, [rax+8]
0x180043b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b6c  mov     rax, [rbx]
0x180043b6f  mov     rcx, rbx
0x180043b72  mov     rax, [rax+8]
0x180043b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b7b  mov     rax, [rbx]
0x180043b7e  mov     rcx, rbx
0x180043b81  mov     rax, [rax+8]
0x180043b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b8a  mov     rax, [rbx]
0x180043b8d  mov     rcx, rbx
0x180043b90  mov     rax, [rax+10h]
0x180043b94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b99  mov     dword ptr [rbx+18h], 17h
0x180043ba0  movdqu  xmmword ptr [rbx+20h], xmm6
0x180043ba5  mov     rcx, [rbx+30h]
0x180043ba9  test    rcx, rcx
0x180043bac  jz      short loc_180043BC2
0x180043bae  mov     rax, [rcx]
0x180043bb1  mov     rax, [rax+10h]
0x180043bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bba  mov     qword ptr [rbx+30h], 0
0x180043bc2  mov     [rbx+38h], ebp
0x180043bc5  mov     rdx, rbx
0x180043bc8  mov     [rbx+3Ch], esi
0x180043bcb  mov     rcx, [rdi+0D0h]
0x180043bd2  mov     rax, [rcx]
0x180043bd5  mov     rax, [rax+28h]
0x180043bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043bde  test    eax, eax
0x180043be0  jns     short loc_180043BF8
0x180043be2  mov     r9d, 20F9h
0x180043be8  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180043bef  xor     edx, edx
0x180043bf1  mov     ecx, eax
0x180043bf3  call    Log_HREvent_7
0x180043bf8  mov     rax, [rbx]
0x180043bfb  mov     rcx, rbx
0x180043bfe  mov     rax, [rax+10h]
0x180043c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c07  jmp     short loc_180043C3D
0x180043c09  mov     ebx, 8007000Eh
0x180043c0e  lea     r8, aOnecoreuapNetP_24; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180043c15  mov     ecx, ebx
0x180043c17  mov     r9d, 535h
0x180043c1d  mov     edx, 1
0x180043c22  call    Log_HREvent_7
0x180043c27  mov     r9d, 20FDh
0x180043c2d  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180043c34  xor     edx, edx
0x180043c36  mov     ecx, ebx
0x180043c38  call    Log_HREvent_7
0x180043c3d  mov     rbx, [rsp+58h+arg_10]
0x180043c42  movaps  xmm6, [rsp+58h+var_28]
0x180043c47  add     rsp, 40h
0x180043c4b  pop     rdi
0x180043c4c  pop     rsi
0x180043c4d  pop     rbp
0x180043c4e  retn
```
