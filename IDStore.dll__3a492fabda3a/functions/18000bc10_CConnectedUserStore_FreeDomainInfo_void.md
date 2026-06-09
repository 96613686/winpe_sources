# CConnectedUserStore::FreeDomainInfo(void)

- ea: `0x18000bc10`
- end: `0x18000bc40`
- name: `?FreeDomainInfo@CConnectedUserStore@@AEAAXXZ`
- size: `48`
- prototype: `void __fastcall(CConnectedUserStore *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b890`

## callees

- `0x18000bc10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000bc22`
- `ntdll!RtlFreeUnicodeString` at `0x18000bc39`

## pseudocode

```c
void __fastcall CConnectedUserStore::FreeDomainInfo(CConnectedUserStore *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 11) = 0;
  }
  RtlFreeUnicodeString((PUNICODE_STRING)((char *)this + 72));
}

```

## disassembly

```asm
0x18000bc10  push    rbx
0x18000bc12  sub     rsp, 20h
0x18000bc16  mov     rbx, rcx
0x18000bc19  mov     rcx, [rcx+58h]; pv
0x18000bc1d  test    rcx, rcx
0x18000bc20  jz      short loc_18000BC30
0x18000bc22  call    cs:__imp_CoTaskMemFree
0x18000bc28  mov     qword ptr [rbx+58h], 0
0x18000bc30  lea     rcx, [rbx+48h]
0x18000bc34  add     rsp, 20h
0x18000bc38  pop     rbx
0x18000bc39  jmp     cs:__imp_RtlFreeUnicodeString
```
