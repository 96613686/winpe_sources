# CStandardCollectorService::MarshallerShutdown(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x140008a40`
- end: `0x140008af9`
- name: `?MarshallerShutdown@CStandardCollectorService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `185`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140008a40`
- `0x14000a278`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x140008a71`
- `KERNEL32!OpenEventW` at `0x140008a71`
- `KERNEL32!SetEvent` at `0x140008af0`
- `KERNEL32!SetEvent` at `0x140008af0`
- `KERNEL32!GetLastError` at `0x140008a84`
- `KERNEL32!GetLastError` at `0x140008a84`
- `KERNEL32!CloseHandle` at `0x140008ab8`
- `KERNEL32!CloseHandle` at `0x140008ab8`

## string_xrefs

- `0x140008a65`: `VisualStudio.StandardCollectorService170.StopEvent`
- `0x140008ace`: `Signaling idle collector service marshaller shutdown.`
- `0x140008ad5`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Service\StandardCollector.Service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CStandardCollectorService::MarshallerShutdown(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  signed int v3; // edi
  __int64 v4; // rbx
  signed int LastError; // eax

  if ( Timer )
  {
    v3 = 0;
    v4 = (__int64)OpenEventW(2u, 0, L"VisualStudio.StandardCollectorService170.StopEvent");
    if ( !v4 )
    {
      LastError = GetLastError();
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
      v4 = -1;
    }
    if ( v3 >= 0 )
    {
      DiagHubCommon::LogStream::Write(
        _logger,
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Service\\StandardCollector.Service.cpp",
        L"Signaling idle collector service marshaller shutdown.");
      SetEvent((HANDLE)v4);
    }
    if ( v4 != -1 )
      CloseHandle((HANDLE)v4);
  }
}

```

## disassembly

```asm
0x140008a40  test    r8, r8
0x140008a43  jz      locret_140008ACD
0x140008a49  mov     rax, rsp
0x140008a4c  mov     [rax+8], rbx
0x140008a50  mov     [rax+10h], rsi
0x140008a54  push    rdi
0x140008a55  sub     rsp, 30h
0x140008a59  xorps   xmm0, xmm0
0x140008a5c  movups  xmmword ptr [rax-18h], xmm0
0x140008a60  xor     edi, edi
0x140008a62  mov     [rax-10h], edi
0x140008a65  lea     r8, aVisualstudioSt; "VisualStudio.StandardCollectorService17"...
0x140008a6c  xor     edx, edx; bInheritHandle
0x140008a6e  lea     ecx, [rdi+2]; dwDesiredAccess
0x140008a71  call    cs:__imp_OpenEventW
0x140008a77  mov     rbx, rax
0x140008a7a  mov     [rsp+38h+var_18], rax
0x140008a7f  test    rax, rax
0x140008a82  jnz     short loc_140008AA5
0x140008a84  call    cs:__imp_GetLastError
0x140008a8a  movzx   edi, ax
0x140008a8d  or      edi, 80070000h
0x140008a93  test    eax, eax
0x140008a95  cmovle  edi, eax
0x140008a98  mov     [rsp+38h+var_10], edi
0x140008a9c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140008aa0  mov     [rsp+38h+var_18], rbx
0x140008aa5  test    edi, edi
0x140008aa7  setns   sil
0x140008aab  test    edi, edi
0x140008aad  jns     short loc_140008ACE
0x140008aaf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140008ab3  jz      short loc_140008ABE
0x140008ab5  mov     rcx, rbx; hObject
0x140008ab8  call    cs:__imp_CloseHandle
0x140008abe  mov     rbx, [rsp+38h+arg_0]
0x140008ac3  mov     rsi, [rsp+38h+arg_8]
0x140008ac8  add     rsp, 30h
0x140008acc  pop     rdi
0x140008acd  retn
0x140008ace  lea     r8, aSignalingIdleC; "Signaling idle collector service marsha"...
0x140008ad5  lea     rdx, aDAWork1SSource_3; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x140008adc  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; this
0x140008ae3  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x140008ae8  test    sil, sil
0x140008aeb  jz      short loc_140008AAF
0x140008aed  mov     rcx, rbx; hEvent
0x140008af0  call    cs:__imp_SetEvent
0x140008af6  jmp     short loc_140008AAF
```
