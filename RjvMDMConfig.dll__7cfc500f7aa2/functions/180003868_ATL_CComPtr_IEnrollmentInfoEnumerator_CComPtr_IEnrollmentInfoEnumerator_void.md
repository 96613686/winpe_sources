# ATL::CComPtr<IEnrollmentInfoEnumerator>::~CComPtr<IEnrollmentInfoEnumerator>(void)

- ea: `0x180003868`
- end: `0x18000386d`
- name: `??1?$CComPtr@UIEnrollmentInfoEnumerator@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001d121`
- `0x18001d133`
- `0x18001d169`
- `0x18001d17b`
- `0x18001d5be`
- `0x18001d606`
- `0x18001d618`
- `0x18001d684`
- `0x18001d696`

## callees

- `0x180003874`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IEnrollmentInfoEnumerator>::~CComPtr<IEnrollmentInfoEnumerator>(__int64 *a1)
{
  return ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(a1);
}

```

## disassembly

```asm
0x180003868  jmp     ??1?$CComPtrBase@VEnrollment@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Enrollment>::~CComPtrBase<Enrollment>(void)
```
