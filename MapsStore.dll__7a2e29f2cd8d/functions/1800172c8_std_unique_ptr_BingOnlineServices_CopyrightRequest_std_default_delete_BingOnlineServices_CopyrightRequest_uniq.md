# std::unique_ptr<BingOnlineServices::CopyrightRequest,std::default_delete<BingOnlineServices::CopyrightRequest>>::~unique_ptr<BingOnlineServices::CopyrightRequest,std::default_delete<BingOnlineServices::CopyrightRequest>>(void)

- ea: `0x1800172c8`
- end: `0x1800172ed`
- name: `??1?$unique_ptr@VCopyrightRequest@BingOnlineServices@@U?$default_delete@VCopyrightRequest@BingOnlineServices@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x180018968`
- `0x18008dd12`

## callees

- `0x18000d460`
- `0x1800172c8`

## import_xrefs

- `BingOnlineServices!??1CopyrightRequest@BingOnlineServices@@QEAA@XZ` at `0x1800172d9`
- `BingOnlineServices!??1CopyrightRequest@BingOnlineServices@@QEAA@XZ` at `0x1800172d9`

## pseudocode

```c
void __fastcall std::unique_ptr<BingOnlineServices::CopyrightRequest>::~unique_ptr<BingOnlineServices::CopyrightRequest>(
        BingOnlineServices::CopyrightRequest **a1)
{
  BingOnlineServices::CopyrightRequest *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    BingOnlineServices::CopyrightRequest::~CopyrightRequest(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800172c8  push    rbx
0x1800172ca  sub     rsp, 20h
0x1800172ce  mov     rbx, [rcx]
0x1800172d1  test    rbx, rbx
0x1800172d4  jz      short loc_1800172E7
0x1800172d6  mov     rcx, rbx
0x1800172d9  call    cs:__imp_??1CopyrightRequest@BingOnlineServices@@QEAA@XZ; BingOnlineServices::CopyrightRequest::~CopyrightRequest(void)
0x1800172df  mov     rcx, rbx; Block
0x1800172e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800172e7  add     rsp, 20h
0x1800172eb  pop     rbx
0x1800172ec  retn
```
