# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x140007394`
- end: `0x140007405`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `113`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000c038`
- `0x14000c250`

## callees

- `0x140007394`
- `0x14000bdec`

## import_xrefs

- `ntdll!memcpy_s` at `0x1400073d2`
- `ntdll!memcpy_s` at `0x1400073d2`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(
        char *Destination,
        const char *a2,
        wil::details *a3,
        char **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // rdx
  rsize_t v9; // rdx
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_BYTE *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v10];
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x140007394  mov     [rsp+arg_0], rbx
0x140007399  mov     [rsp+arg_8], rsi
0x14000739e  push    rdi
0x14000739f  sub     rsp, 20h
0x1400073a3  mov     rbx, r9
0x1400073a6  mov     rdi, rcx
0x1400073a9  cmp     rcx, rdx
0x1400073ac  jz      short loc_1400073E6
0x1400073ae  test    r8, r8
0x1400073b1  jz      short loc_1400073E6
0x1400073b3  cmp     byte ptr [r8], 0
0x1400073b7  jz      short loc_1400073E6
0x1400073b9  mov     rcx, r8; this
0x1400073bc  call    ?ResultStringSize@details@wil@@YA_KPEBD@Z; wil::details::ResultStringSize(char const *)
0x1400073c1  sub     rdx, rdi; DestinationSize
0x1400073c4  mov     rsi, rax
0x1400073c7  cmp     rdx, rax
0x1400073ca  jb      short loc_1400073E6
0x1400073cc  mov     r9, rax; SourceSize
0x1400073cf  mov     rcx, rdi; Destination
0x1400073d2  call    cs:__imp_memcpy_s
0x1400073d8  test    rbx, rbx
0x1400073db  jz      short loc_1400073E0
0x1400073dd  mov     [rbx], rdi
0x1400073e0  lea     rax, [rsi+rdi]
0x1400073e4  jmp     short loc_1400073F5
0x1400073e6  test    rbx, rbx
0x1400073e9  jz      short loc_1400073F2
0x1400073eb  mov     qword ptr [r9], 0
0x1400073f2  mov     rax, rdi
0x1400073f5  mov     rbx, [rsp+28h+arg_0]
0x1400073fa  mov     rsi, [rsp+28h+arg_8]
0x1400073ff  add     rsp, 20h
0x140007403  pop     rdi
0x140007404  retn
```
