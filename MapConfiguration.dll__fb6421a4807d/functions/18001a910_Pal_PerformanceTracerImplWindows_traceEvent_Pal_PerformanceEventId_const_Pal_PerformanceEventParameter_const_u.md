# Pal::PerformanceTracerImplWindows::traceEvent(Pal::PerformanceEventId const &,Pal::PerformanceEventParameter const *,unsigned __int64,char *)

- ea: `0x18001a910`
- end: `0x18001aa0b`
- name: `?traceEvent@PerformanceTracerImplWindows@Pal@@UEAAXAEBVPerformanceEventId@2@PEBVPerformanceEventParameter@2@_KPEAD@Z`
- size: `251`
- prototype: `void(Pal::PerformanceTracerImplWindows *__hidden this, const struct Pal::PerformanceEventId *, const struct Pal::PerformanceEventParameter *, unsigned __int64, char *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800094a0`
- `0x18000a074`
- `0x18001a910`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a9e2`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x18001a9e2`

## pseudocode

```c
void __fastcall Pal::PerformanceTracerImplWindows::traceEvent(
        Pal::PerformanceTracerImplWindows *this,
        const struct Pal::PerformanceEventId *a2,
        const struct Pal::PerformanceEventParameter *a3,
        unsigned __int64 a4)
{
  unsigned __int64 i; // rdx
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // rdx
  _QWORD v12[34]; // [rsp+20h] [rbp-138h] BYREF

  if ( a4 < 0x11 && *((_BYTE *)this + 8) )
  {
    memset_0(v12, 0, sizeof(v12));
    for ( i = 0; i < a4; HIDWORD(v12[v9 + 1]) = 0 )
    {
      v9 = i++;
      v9 *= 2LL;
      v12[v9] = *((_QWORD *)a3 + v9);
      LODWORD(v12[v9 + 1]) = *((_DWORD *)a3 + 2 * v9 + 2);
    }
    v10 = *(unsigned int *)a2;
    if ( v10 < 0xAAAAAAAAAAAAAAABuLL
             * ((__int64)(*((_QWORD *)&Pal::PerformanceEventIdToEventDescriptorMapping<_EVENT_DESCRIPTOR>::sEventIdToEventDescriptorMapping
                          + 1)
                        - Pal::PerformanceEventIdToEventDescriptorMapping<_EVENT_DESCRIPTOR>::sEventIdToEventDescriptorMapping) >> 3) )
    {
      v11 = Pal::PerformanceEventIdToEventDescriptorMapping<_EVENT_DESCRIPTOR>::sEventIdToEventDescriptorMapping
          + 24 * v10;
      if ( *(_BYTE *)(v11 + 16) )
        EventWrite(
          *((_QWORD *)this + 2),
          (PCEVENT_DESCRIPTOR)v11,
          a4,
          (PEVENT_DATA_DESCRIPTOR)((unsigned __int64)v12 & -(__int64)(a4 != 0)));
    }
  }
}

```

## disassembly

```asm
0x18001a910  cmp     r9, 11h
0x18001a914  jnb     locret_18001AA0A
0x18001a91a  mov     [rsp+arg_10], rbx
0x18001a91f  push    rbp
0x18001a920  push    rsi
0x18001a921  push    rdi
0x18001a922  sub     rsp, 140h
0x18001a929  mov     rax, cs:__security_cookie
0x18001a930  xor     rax, rsp
0x18001a933  mov     [rsp+158h+var_28], rax
0x18001a93b  cmp     byte ptr [rcx+8], 0
0x18001a93f  mov     rbx, r9
0x18001a942  mov     rsi, r8
0x18001a945  mov     rbp, rdx
0x18001a948  mov     rdi, rcx
0x18001a94b  jz      loc_18001A9E8
0x18001a951  xor     edx, edx; Val
0x18001a953  lea     rcx, [rsp+158h+var_138]; void *
0x18001a958  mov     r8d, 110h; Size
0x18001a95e  call    memset_0
0x18001a963  xor     edx, edx
0x18001a965  test    rbx, rbx
0x18001a968  jz      short loc_18001A991
0x18001a96a  mov     rcx, rdx
0x18001a96d  inc     rdx
0x18001a970  add     rcx, rcx
0x18001a973  mov     rax, [rsi+rcx*8]
0x18001a977  mov     [rsp+rcx*8+158h+var_138], rax
0x18001a97c  mov     eax, [rsi+rcx*8+8]
0x18001a980  mov     [rsp+rcx*8+158h+var_130], eax
0x18001a984  mov     [rsp+rcx*8+158h+var_12C], 0
0x18001a98c  cmp     rdx, rbx
0x18001a98f  jb      short loc_18001A96A
0x18001a991  mov     rax, qword ptr cs:?sEventIdToEventDescriptorMapping@?$PerformanceEventIdToEventDescriptorMapping@U_EVENT_DESCRIPTOR@@@Pal@@0V?$SimpleMap@IU_EVENT_DESCRIPTOR@@@Core@@A+8; Core::SimpleMap<uint,_EVENT_DESCRIPTOR> Pal::PerformanceEventIdToEventDescriptorMapping<_EVENT_DESCRIPTOR>::sEventIdToEventDescriptorMapping
0x18001a998  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18001a9a2  mov     r8, qword ptr cs:?sEventIdToEventDescriptorMapping@?$PerformanceEventIdToEventDescriptorMapping@U_EVENT_DESCRIPTOR@@@Pal@@0V?$SimpleMap@IU_EVENT_DESCRIPTOR@@@Core@@A; Core::SimpleMap<uint,_EVENT_DESCRIPTOR> Pal::PerformanceEventIdToEventDescriptorMapping<_EVENT_DESCRIPTOR>::sEventIdToEventDescriptorMapping
0x18001a9a9  mov     edx, [rbp+0]
0x18001a9ac  sub     rax, r8
0x18001a9af  sar     rax, 3
0x18001a9b3  imul    rax, rcx
0x18001a9b7  cmp     rdx, rax
0x18001a9ba  jnb     short loc_18001A9E8
0x18001a9bc  lea     rax, [rdx+rdx*2]
0x18001a9c0  lea     rdx, [r8+rax*8]; EventDescriptor
0x18001a9c4  cmp     byte ptr [rdx+10h], 0
0x18001a9c8  jz      short loc_18001A9E8
0x18001a9ca  mov     rcx, [rdi+10h]; RegHandle
0x18001a9ce  mov     rax, rbx
0x18001a9d1  neg     rax
0x18001a9d4  mov     r8d, ebx; UserDataCount
0x18001a9d7  lea     rax, [rsp+158h+var_138]
0x18001a9dc  sbb     r9, r9
0x18001a9df  and     r9, rax; UserData
0x18001a9e2  call    cs:__imp_EventWrite
0x18001a9e8  mov     rcx, [rsp+158h+var_28]
0x18001a9f0  xor     rcx, rsp; StackCookie
0x18001a9f3  call    __security_check_cookie
0x18001a9f8  mov     rbx, [rsp+158h+arg_10]
0x18001aa00  add     rsp, 140h
0x18001aa07  pop     rdi
0x18001aa08  pop     rsi
0x18001aa09  pop     rbp
0x18001aa0a  retn
```
