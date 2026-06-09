# winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::Workload>::~com_ptr<winrt::Microsoft::Windows::Workloads::implementation::Workload>(void)

- ea: `0x180018da0`
- end: `0x180018dab`
- name: `??1?$com_ptr@UWorkload@implementation@Workloads@Windows@Microsoft@winrt@@@winrt@@QEAA@XZ`
- size: `11`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003eaf9`
- `0x180040e70`
- `0x180041120`
- `0x180041620`

## callees

- `0x18000e550`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::Workload>::~com_ptr<winrt::Microsoft::Windows::Workloads::implementation::Workload>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref();
  return result;
}

```

## disassembly

```asm
0x180018da0  cmp     qword ptr [rcx], 0
0x180018da4  jnz     ?unconditional_release_ref@?$com_ptr@UWorkloadManager@implementation@Workloads@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager>::unconditional_release_ref(void)
0x180018daa  retn
```
