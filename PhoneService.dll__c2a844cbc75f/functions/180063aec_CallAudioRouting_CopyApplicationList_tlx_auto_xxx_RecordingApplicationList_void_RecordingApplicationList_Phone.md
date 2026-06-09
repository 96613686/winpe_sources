# CallAudioRouting::_CopyApplicationList(tlx::auto_xxx<RecordingApplicationList *,void (*)(RecordingApplicationList *),&PhoneFreeRecordingApplicationList(RecordingApplicationList *),0> &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,int *,ushort *,uint)

- ea: `0x180063aec`
- end: `0x180063eba`
- name: `?_CopyApplicationList@CallAudioRouting@@AEAAJAEAV?$auto_xxx@PEAURecordingApplicationList@@P6AXPEAU1@@Z$1?PhoneFreeRecordingApplicationList@@YAX0@Z$0A@@tlx@@AEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEAHPEAGI@Z`
- size: `974`
- prototype: `__int64 __usercall@<rax>(CallAudioRouting *this@<rcx>, unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18005ebf0`

## callees

- `0x180006e94`
- `0x18000bb40`
- `0x18005f9c0`
- `0x180063a78`
- `0x180063aec`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063b31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180063b31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e96`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180063e96`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063b8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063cd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063d12`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063b8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063cd6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180063d12`

## string_xrefs

- `0x180063e22`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180063e53`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`
- `0x180063e80`: `onecoreuap\net\phone\phoneservice\service\lib\callaudiorouting.cpp`

## pseudocode

```c

```
