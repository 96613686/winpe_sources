# ATL::CComClassFactorySingleton<CRemoteAssistance>::~CComClassFactorySingleton<CRemoteAssistance>(void)

- ea: `0x1400033dc`
- end: `0x140003410`
- name: `??1?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003580`

## callees

- `0x1400035c8`
- `0x1400039e0`

## pseudocode

```c
void __fastcall ATL::CComClassFactorySingleton<CRemoteAssistance>::~CComClassFactorySingleton<CRemoteAssistance>(
        _QWORD *a1)
{
  *a1 = &ATL::CComClassFactorySingleton<CRemoteAssistance>::`vftable';
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1 + 10);
  *a1 = &ATL::CComClassFactory::`vftable';
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 2));
}

```

## disassembly

```asm
0x1400033dc  push    rbx
0x1400033de  sub     rsp, 20h
0x1400033e2  lea     rax, ??_7?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@6B@; const ATL::CComClassFactorySingleton<CRemoteAssistance>::`vftable'
0x1400033e9  mov     rbx, rcx
0x1400033ec  mov     [rcx], rax
0x1400033ef  add     rcx, 50h ; 'P'
0x1400033f3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400033f8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1400033ff  lea     rcx, [rbx+10h]; this
0x140003403  mov     [rbx], rax
0x140003406  add     rsp, 20h
0x14000340a  pop     rbx
0x14000340b  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
