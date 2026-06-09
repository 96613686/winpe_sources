# Uev::SmartHandle<wchar_t *,&Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>::~SmartHandle<wchar_t *,&Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>(void)

- ea: `0x140087d10`
- end: `0x140087d34`
- name: `??1?$SmartHandle@PEA_W$1?CoTaskMemFreeWrapper@Path@Uev@@CAXPEA_W@Z$0A@@Uev@@QEAA@XZ`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14008843c`
- `0x1400985b1`

## callees

- `0x140087d10`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x140087d21`
- `ole32!CoTaskMemFree` at `0x140087d21`

## pseudocode

```c
void __fastcall Uev::SmartHandle<wchar_t *,&private: static void Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>::~SmartHandle<wchar_t *,&private: static void Uev::Path::CoTaskMemFreeWrapper(wchar_t *),0>(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140087d10  push    rbx
0x140087d12  sub     rsp, 20h
0x140087d16  mov     rbx, rcx
0x140087d19  mov     rcx, [rcx]; pv
0x140087d1c  test    rcx, rcx
0x140087d1f  jz      short loc_140087D2E
0x140087d21  call    cs:__imp_CoTaskMemFree
0x140087d27  mov     qword ptr [rbx], 0
0x140087d2e  add     rsp, 20h
0x140087d32  pop     rbx
0x140087d33  retn
```
