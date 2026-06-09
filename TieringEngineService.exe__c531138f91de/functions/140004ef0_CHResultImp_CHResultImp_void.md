# CHResultImp::CHResultImp(void)

- ea: `0x140004ef0`
- end: `0x140004f98`
- name: `??0CHResultImp@@QEAA@XZ`
- size: `168`
- prototype: `CHResultImp *__fastcall(CHResultImp *__hidden this)`
- caller_count: `92`
- callee_count: `2`
- tags: ``

## callers

- `0x1400052f0`
- `0x140006720`
- `0x14000761c`
- `0x140007c90`
- `0x140007f18`
- `0x140008e04`
- `0x140008fe4`
- `0x1400094f8`
- `0x14000a560`
- `0x14000a700`
- `0x14000acac`
- `0x14000b0d0`
- `0x14000b490`
- `0x14000b960`
- `0x14000c444`
- `0x14000c648`
- `0x14000c8f8`
- `0x14000ce48`
- `0x14000d804`
- `0x14000de58`
- `0x14000e6c0`
- `0x14000ea7c`
- `0x14000ef74`
- `0x14000f108`
- `0x14000f728`
- `0x14000f97c`
- `0x1400104f4`
- `0x1400108e0`
- `0x140010d1c`
- `0x140012040`
- `0x1400122fc`
- `0x14001250c`
- `0x140014fe4`
- `0x140015ff0`
- `0x1400164c8`
- `0x140016d18`
- `0x140017120`
- `0x1400194ec`
- `0x14001a050`
- `0x14001a270`
- `0x14001b328`
- `0x14001c094`
- `0x14001cb9c`
- `0x14001d5a4`
- `0x14001d7ec`
- `0x14001da7c`
- `0x14001dbf0`
- `0x14001e2e0`
- `0x14001effc`
- `0x14001f874`

## callees

- `0x140004ef0`
- `0x140009c80`

## pseudocode

```c
CHResultImp *__fastcall CHResultImp::CHResultImp(CHResultImp *this)
{
  PVOID ThreadLocalStoragePointer; // rax
  __int64 v3; // r8

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  *((_DWORD *)this + 2) = 0;
  v3 = *(_QWORD *)(*(_QWORD *)ThreadLocalStoragePointer + 8LL);
  ++*(_WORD *)(*(_QWORD *)ThreadLocalStoragePointer + 16LL);
  *(_QWORD *)this = v3;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_Zs(*((_QWORD *)WPP_GLOBAL_Control + 2), v3);
  }
  return this;
}

```

## disassembly

```asm
0x140004ef0  push    rbx
0x140004ef2  sub     rsp, 40h
0x140004ef6  mov     rax, gs:58h
0x140004eff  mov     rbx, rcx
0x140004f02  mov     r8d, 8
0x140004f08  mov     dword ptr [rcx+8], 0
0x140004f0f  mov     rdx, [rax]
0x140004f12  mov     eax, 10h
0x140004f17  mov     r8, [r8+rdx]
0x140004f1b  inc     word ptr [rax+rdx]
0x140004f1f  movzx   eax, word ptr [rax+rdx]
0x140004f23  movzx   edx, cs:?GlobalIndentString@@3U_UNICODE_STRING@@A; _UNICODE_STRING GlobalIndentString
0x140004f2a  add     rax, rax
0x140004f2d  mov     [rcx], r8
0x140004f30  cmp     rax, rdx
0x140004f33  jnb     short loc_140004F41
0x140004f35  mov     [rsp+48h+var_18], ax
0x140004f3a  mov     [rsp+48h+var_16], ax
0x140004f3f  jmp     short loc_140004F4B
0x140004f41  mov     [rsp+48h+var_18], dx
0x140004f46  mov     [rsp+48h+var_16], dx
0x140004f4b  xor     eax, eax
0x140004f4d  mov     [rsp+48h+var_14], eax
0x140004f51  mov     rax, cs:off_14004C120; "                                       "...
0x140004f58  mov     [rsp+48h+var_10], rax
0x140004f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f64  lea     rax, WPP_GLOBAL_Control
0x140004f6b  cmp     rcx, rax
0x140004f6e  jz      short loc_140004F8F
0x140004f70  test    byte ptr [rcx+1Ch], 1
0x140004f74  jz      short loc_140004F8F
0x140004f76  cmp     byte ptr [rcx+19h], 5
0x140004f7a  jb      short loc_140004F8F
0x140004f7c  mov     rcx, [rcx+10h]; LoggerHandle
0x140004f80  lea     r9, [rsp+48h+var_18]
0x140004f85  mov     [rsp+48h+var_28], r8; __int64
0x140004f8a  call    WPP_SF_Zs
0x140004f8f  mov     rax, rbx
0x140004f92  add     rsp, 40h
0x140004f96  pop     rbx
0x140004f97  retn
```
