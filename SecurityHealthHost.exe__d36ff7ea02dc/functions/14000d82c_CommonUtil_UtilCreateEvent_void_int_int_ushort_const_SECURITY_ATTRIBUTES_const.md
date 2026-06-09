# CommonUtil::UtilCreateEvent(void * *,int,int,ushort const *,_SECURITY_ATTRIBUTES const *)

- ea: `0x14000d82c`
- end: `0x14000d893`
- name: `?UtilCreateEvent@CommonUtil@@YAJPEAPEAXHHPEBGPEBU_SECURITY_ATTRIBUTES@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(CommonUtil *this, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002a94`

## callees

- `0x140003040`
- `0x14000d82c`
- `0x14000f7c8`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14000d841`
- `KERNEL32!CreateEventW` at `0x14000d841`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilCreateEvent(CommonUtil *this, void **a2)
{
  HANDLE EventW; // rax
  unsigned int LastFailure; // ebx

  EventW = CreateEventW(0, 1, 0, 0);
  *(_QWORD *)this = EventW;
  if ( EventW )
    return 0;
  LastFailure = HrGetLastFailure();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids, LastFailure);
  return LastFailure;
}

```

## disassembly

```asm
0x14000d82c  push    rbx
0x14000d82e  sub     rsp, 20h
0x14000d832  xor     r9d, r9d; lpName
0x14000d835  mov     rbx, rcx
0x14000d838  xor     r8d, r8d; bInitialState
0x14000d83b  xor     ecx, ecx; lpEventAttributes
0x14000d83d  lea     edx, [r9+1]; bManualReset
0x14000d841  call    cs:__imp_CreateEventW
0x14000d847  mov     [rbx], rax
0x14000d84a  test    rax, rax
0x14000d84d  jnz     short loc_14000D88B
0x14000d84f  call    HrGetLastFailure
0x14000d854  mov     ebx, eax
0x14000d856  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d85d  lea     rax, WPP_GLOBAL_Control
0x14000d864  cmp     rcx, rax
0x14000d867  jz      short loc_14000D887
0x14000d869  test    byte ptr [rcx+1Ch], 1
0x14000d86d  jz      short loc_14000D887
0x14000d86f  mov     rcx, [rcx+10h]
0x14000d873  lea     r8, WPP_b11265c829643c9fe11ce3dfb10c34a9_Traceguids
0x14000d87a  mov     edx, 0Bh
0x14000d87f  mov     r9d, ebx
0x14000d882  call    WPP_SF_d
0x14000d887  mov     eax, ebx
0x14000d889  jmp     short loc_14000D88D
0x14000d88b  xor     eax, eax
0x14000d88d  add     rsp, 20h
0x14000d891  pop     rbx
0x14000d892  retn
```
