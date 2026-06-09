# WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::~CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>(void)

- ea: `0x180041a08`
- end: `0x180041a60`
- name: `??1?$CEnumControlWarningInfoImpl@VCControlManager@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@UEAA@XZ`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180041554`
- `0x1800857a9`

## callees

- `0x18000c720`
- `0x1800328f8`
- `0x180041a08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041a23`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180041a23`

## pseudocode

```c
void __fastcall WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::~CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>(
        __int64 a1)
{
  void *v2; // rcx

  WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo(a1);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v2 = *(void **)(a1 + 8);
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*(_QWORD *)(a1 + 24) - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF8uLL);
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
  }
}

```

## disassembly

```asm
0x180041a08  push    rbx
0x180041a0a  sub     rsp, 30h
0x180041a0e  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180041a17  mov     rbx, rcx
0x180041a1a  call    ?ClearControlWarningInfo@?$CEnumControlWarningInfoImpl@VCControlManager@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAXXZ; WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo(void)
0x180041a1f  lea     rcx, [rbx+28h]; lpCriticalSection
0x180041a23  call    cs:__imp_DeleteCriticalSection
0x180041a29  mov     rcx, [rbx+8]
0x180041a2d  test    rcx, rcx
0x180041a30  jz      short loc_180041A5A
0x180041a32  mov     rdx, [rbx+18h]
0x180041a36  sub     rdx, rcx
0x180041a39  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180041a3d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180041a42  mov     qword ptr [rbx+8], 0
0x180041a4a  mov     qword ptr [rbx+10h], 0
0x180041a52  mov     qword ptr [rbx+18h], 0
0x180041a5a  add     rsp, 30h
0x180041a5e  pop     rbx
0x180041a5f  retn
```
