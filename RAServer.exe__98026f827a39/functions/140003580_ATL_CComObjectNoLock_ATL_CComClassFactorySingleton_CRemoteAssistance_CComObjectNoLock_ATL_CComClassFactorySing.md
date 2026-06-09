# ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::~CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>(void)

- ea: `0x140003580`
- end: `0x140003596`
- name: `??1?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@QEAA@XZ`
- size: `22`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140003f00`

## callees

- `0x1400033dc`

## pseudocode

```c
void __fastcall ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::~CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>(
        _QWORD *a1)
{
  *((_DWORD *)a1 + 2) = -1073741823;
  *a1 = &ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`vftable';
  ATL::CComClassFactorySingleton<CRemoteAssistance>::~CComClassFactorySingleton<CRemoteAssistance>(a1);
}

```

## disassembly

```asm
0x140003580  lea     rax, ??_7?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::`vftable'
0x140003587  mov     dword ptr [rcx+8], 0C0000001h
0x14000358e  mov     [rcx], rax
0x140003591  jmp     ??1?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@QEAA@XZ; ATL::CComClassFactorySingleton<CRemoteAssistance>::~CComClassFactorySingleton<CRemoteAssistance>(void)
```
