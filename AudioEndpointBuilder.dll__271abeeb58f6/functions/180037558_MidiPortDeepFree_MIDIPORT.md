# MidiPortDeepFree(_MIDIPORT *)

- ea: `0x180037558`
- end: `0x180037591`
- name: `?MidiPortDeepFree@@YAXPEAU_MIDIPORT@@@Z`
- size: `57`
- prototype: `void __fastcall(struct _MIDIPORT *pv)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022b30`
- `0x180022d38`
- `0x180037790`
- `0x18004986c`
- `0x18004c2b4`

## callees

- `0x180037558`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037569`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003757c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037585`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037569`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003757c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037585`

## pseudocode

```c
void __fastcall MidiPortDeepFree(LPVOID *pv)
{
  if ( pv )
  {
    CoTaskMemFree(pv[5]);
    CoTaskMemFree(pv[4]);
    CoTaskMemFree(*pv);
    CoTaskMemFree(pv);
  }
}

```

## disassembly

```asm
0x180037558  test    rcx, rcx
0x18003755b  jz      short locret_180037590
0x18003755d  push    rbx
0x18003755e  sub     rsp, 20h
0x180037562  mov     rbx, rcx
0x180037565  mov     rcx, [rcx+28h]; pv
0x180037569  call    cs:__imp_CoTaskMemFree
0x18003756f  mov     rcx, [rbx+20h]; pv
0x180037573  call    cs:__imp_CoTaskMemFree
0x180037579  mov     rcx, [rbx]; pv
0x18003757c  call    cs:__imp_CoTaskMemFree
0x180037582  mov     rcx, rbx; pv
0x180037585  call    cs:__imp_CoTaskMemFree
0x18003758b  add     rsp, 20h
0x18003758f  pop     rbx
0x180037590  retn
```
