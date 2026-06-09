# ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA(void)

- ea: `0x180006228`
- end: `0x180006341`
- name: `??1ON_CREATE_PROC_DATA@@QEAA@XZ`
- size: `281`
- prototype: `void __fastcall(void **this)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, loader_planting`

## callers

- `0x180006164`
- `0x180006860`
- `0x1800078a0`
- `0x180008578`

## callees

- `0x180006228`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000624b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000627d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006305`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000624b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000627d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800062e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006305`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000632f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000632f`

## pseudocode

```c
void __fastcall ON_CREATE_PROC_DATA::~ON_CREATE_PROC_DATA(void **this)
{
  void *v2; // rcx
  void *v3; // rcx

  if ( (unsigned __int64)this[29] >= 8 )
    operator delete(this[26]);
  this[29] = (void *)7;
  this[28] = 0;
  *((_WORD *)this + 104) = 0;
  v2 = this[23];
  if ( v2 )
  {
    operator delete(v2);
    this[23] = 0;
    this[24] = 0;
    this[25] = 0;
  }
  v3 = this[20];
  if ( v3 )
  {
    operator delete(v3);
    this[20] = 0;
    this[21] = 0;
    this[22] = 0;
  }
  if ( (unsigned __int64)this[8] >= 8 )
    operator delete(this[5]);
  this[8] = (void *)7;
  this[7] = 0;
  *((_WORD *)this + 20) = 0;
  if ( (unsigned __int64)this[4] >= 8 )
    operator delete(this[1]);
  this[4] = (void *)7;
  this[3] = 0;
  *((_WORD *)this + 4) = 0;
  if ( (char *)*this - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(*this);
}

```

## disassembly

```asm
0x180006228  mov     [rsp+arg_8], rbx
0x18000622d  mov     [rsp+arg_0], rcx
0x180006232  push    rsi
0x180006233  sub     rsp, 20h
0x180006237  mov     rbx, rcx
0x18000623a  cmp     qword ptr [rcx+0E8h], 8
0x180006242  jb      short loc_180006251
0x180006244  mov     rcx, [rcx+0D0h]
0x18000624b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006251  mov     esi, 7
0x180006256  mov     [rbx+0E8h], rsi
0x18000625d  mov     qword ptr [rbx+0E0h], 0
0x180006268  xor     eax, eax
0x18000626a  mov     [rbx+0D0h], ax
0x180006271  mov     rcx, [rbx+0B8h]
0x180006278  test    rcx, rcx
0x18000627b  jz      short loc_1800062A4
0x18000627d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006283  mov     qword ptr [rbx+0B8h], 0
0x18000628e  mov     qword ptr [rbx+0C0h], 0
0x180006299  mov     qword ptr [rbx+0C8h], 0
0x1800062a4  mov     rcx, [rbx+0A0h]
0x1800062ab  test    rcx, rcx
0x1800062ae  jz      short loc_1800062D7
0x1800062b0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062b6  mov     qword ptr [rbx+0A0h], 0
0x1800062c1  mov     qword ptr [rbx+0A8h], 0
0x1800062cc  mov     qword ptr [rbx+0B0h], 0
0x1800062d7  cmp     qword ptr [rbx+40h], 8
0x1800062dc  jb      short loc_1800062E8
0x1800062de  mov     rcx, [rbx+28h]
0x1800062e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800062e8  mov     [rbx+40h], rsi
0x1800062ec  mov     qword ptr [rbx+38h], 0
0x1800062f4  xor     eax, eax
0x1800062f6  mov     [rbx+28h], ax
0x1800062fa  cmp     qword ptr [rbx+20h], 8
0x1800062ff  jb      short loc_18000630B
0x180006301  mov     rcx, [rbx+8]
0x180006305  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000630b  mov     [rbx+20h], rsi
0x18000630f  mov     qword ptr [rbx+18h], 0
0x180006317  xor     eax, eax
0x180006319  mov     [rbx+8], ax
0x18000631d  mov     [rsp+28h+arg_0], rbx
0x180006322  mov     rcx, [rbx]; hObject
0x180006325  lea     rax, [rcx-1]
0x180006329  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000632d  ja      short loc_180006336
0x18000632f  call    cs:__imp_CloseHandle
0x180006335  nop
0x180006336  mov     rbx, [rsp+28h+arg_8]
0x18000633b  add     rsp, 20h
0x18000633f  pop     rsi
0x180006340  retn
```
