# WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup(void)

- ea: `0x180059970`
- end: `0x1800599b9`
- name: `?Cleanup@CMarkSession@CControlManager@WindowsPerformanceRecorder@@AEAAXXZ`
- size: `73`
- prototype: `void __fastcall(WindowsPerformanceRecorder::CControlManager::CMarkSession *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18003a1f0`
- `0x180057b00`
- `0x18005c0dc`
- `0x18005deb0`

## callees

- `0x18001d190`
- `0x1800581cc`
- `0x180059970`
- `0x18005eb94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005999f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005999f`

## pseudocode

```c
void __fastcall WindowsPerformanceRecorder::CControlManager::CMarkSession::Cleanup(
        WindowsPerformanceRecorder::CETWProperties::CEventSession **this)
{
  unsigned int v2; // edx
  const WCHAR *FileName; // rax
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v4; // rcx

  if ( this[1] )
  {
    WindowsPerformanceRecorder::CControlManager::CMarkSession::Stop((WindowsPerformanceRecorder::CControlManager::CMarkSession *)this);
    if ( WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(this[1]) )
    {
      FileName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(this[1]);
      DeleteFileW(FileName);
    }
    v4 = this[1];
    if ( v4 )
      WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(v4, v2);
  }
}

```

## disassembly

```asm
0x180059970  push    rbx
0x180059972  sub     rsp, 20h
0x180059976  cmp     qword ptr [rcx+8], 0
0x18005997b  mov     rbx, rcx
0x18005997e  jz      short loc_1800599B3
0x180059980  call    ?Stop@CMarkSession@CControlManager@WindowsPerformanceRecorder@@QEAAJXZ; WindowsPerformanceRecorder::CControlManager::CMarkSession::Stop(void)
0x180059985  mov     rcx, [rbx+8]; this
0x180059989  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x18005998e  test    rax, rax
0x180059991  jz      short loc_1800599A5
0x180059993  mov     rcx, [rbx+8]; this
0x180059997  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x18005999c  mov     rcx, rax; lpFileName
0x18005999f  call    cs:__imp_DeleteFileW
0x1800599a5  mov     rcx, [rbx+8]; this
0x1800599a9  test    rcx, rcx
0x1800599ac  jz      short loc_1800599B3
0x1800599ae  call    ??_GCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAAPEAXI@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(uint)
0x1800599b3  add     rsp, 20h
0x1800599b7  pop     rbx
0x1800599b8  retn
```
