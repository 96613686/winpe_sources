# CHResultImp::~CHResultImp(void)

- ea: `0x140005420`
- end: `0x1400054fb`
- name: `??1CHResultImp@@QEAA@XZ`
- size: `219`
- prototype: `void __fastcall(CHResultImp *__hidden this)`
- caller_count: `101`
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

- `0x140005420`
- `0x140009d40`

## pseudocode

```c
void __fastcall CHResultImp::~CHResultImp(CHResultImp *this)
{
  __int64 v2; // rbx
  int v3; // r8d
  _QWORD *v4; // rcx

  v2 = *(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer;
  v3 = *((_DWORD *)this + 2);
  if ( v3 >= 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      goto LABEL_9;
    }
  }
  else
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
LABEL_9:
      WPP_SF_Zsd(v4[2], *(_QWORD *)this, v3);
    }
  }
  --*(_WORD *)(v2 + 16);
}

```

## disassembly

```asm
0x140005420  mov     [rsp+arg_0], rbx
0x140005425  push    rdi
0x140005426  sub     rsp, 40h
0x14000542a  mov     rax, gs:58h
0x140005433  mov     r9, rcx
0x140005436  movzx   edx, cs:?GlobalIndentString@@3U_UNICODE_STRING@@A; _UNICODE_STRING GlobalIndentString
0x14000543d  mov     edi, 10h
0x140005442  mov     rbx, [rax]
0x140005445  movzx   eax, word ptr [rdi+rbx]
0x140005449  add     rax, rax
0x14000544c  cmp     rax, rdx
0x14000544f  jnb     short loc_14000545D
0x140005451  mov     [rsp+48h+var_18], ax
0x140005456  mov     [rsp+48h+var_16], ax
0x14000545b  jmp     short loc_140005467
0x14000545d  mov     [rsp+48h+var_18], dx
0x140005462  mov     [rsp+48h+var_16], dx
0x140005467  mov     r8d, [rcx+8]
0x14000546b  xor     eax, eax
0x14000546d  mov     [rsp+48h+var_14], eax
0x140005471  mov     rax, cs:off_14004C120; "                                       "...
0x140005478  mov     [rsp+48h+var_10], rax
0x14000547d  test    r8d, r8d
0x140005480  jns     short loc_1400054A8
0x140005482  mov     rcx, cs:WPP_GLOBAL_Control
0x140005489  lea     rax, WPP_GLOBAL_Control
0x140005490  cmp     rcx, rax
0x140005493  jz      short loc_1400054E7
0x140005495  test    byte ptr [rcx+1Ch], 1
0x140005499  jz      short loc_1400054E7
0x14000549b  cmp     byte ptr [rcx+19h], 2
0x14000549f  jb      short loc_1400054E7
0x1400054a1  mov     edx, 0Eh
0x1400054a6  jmp     short loc_1400054CC
0x1400054a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054af  lea     rax, WPP_GLOBAL_Control
0x1400054b6  cmp     rcx, rax
0x1400054b9  jz      short loc_1400054E7
0x1400054bb  test    byte ptr [rcx+1Ch], 1
0x1400054bf  jz      short loc_1400054E7
0x1400054c1  cmp     byte ptr [rcx+19h], 5
0x1400054c5  jb      short loc_1400054E7
0x1400054c7  mov     edx, 0Fh
0x1400054cc  mov     rax, [r9]
0x1400054cf  lea     r9, [rsp+48h+var_18]
0x1400054d4  mov     rcx, [rcx+10h]; LoggerHandle
0x1400054d8  mov     dword ptr [rsp+48h+var_20], r8d; char
0x1400054dd  mov     [rsp+48h+var_28], rax; __int64
0x1400054e2  call    WPP_SF_Zsd
0x1400054e7  mov     eax, 0FFFFh
0x1400054ec  add     [rdi+rbx], ax
0x1400054f0  mov     rbx, [rsp+48h+arg_0]
0x1400054f5  add     rsp, 40h
0x1400054f9  pop     rdi
0x1400054fa  retn
```
