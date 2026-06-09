# DiagHubCommon::ComHelper::~ComHelper(void)

- ea: `0x140002440`
- end: `0x14000245d`
- name: `??1ComHelper@DiagHubCommon@@QEAA@XZ`
- size: `29`
- prototype: `void __fastcall(DiagHubCommon::ComHelper *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014cae`
- `0x140014d7b`
- `0x14001509c`
- `0x14001517c`

## callees

- `0x140002440`

## import_xrefs

- `ole32!CoUninitialize` at `0x14000244e`
- `ole32!CoUninitialize` at `0x14000244e`

## pseudocode

```c
void __fastcall DiagHubCommon::ComHelper::~ComHelper(DiagHubCommon::ComHelper *this)
{
  if ( *(_BYTE *)this )
  {
    CoUninitialize();
    *(_BYTE *)this = 0;
  }
}

```

## disassembly

```asm
0x140002440  push    rbx
0x140002442  sub     rsp, 20h
0x140002446  cmp     byte ptr [rcx], 0
0x140002449  mov     rbx, rcx
0x14000244c  jz      short loc_140002457
0x14000244e  call    cs:__imp_CoUninitialize
0x140002454  mov     byte ptr [rbx], 0
0x140002457  add     rsp, 20h
0x14000245b  pop     rbx
0x14000245c  retn
```
