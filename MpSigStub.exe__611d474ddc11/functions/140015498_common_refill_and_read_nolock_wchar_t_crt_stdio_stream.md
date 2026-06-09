# common_refill_and_read_nolock<wchar_t>(__crt_stdio_stream)

- ea: `0x140015498`
- end: `0x140015639`
- name: `??$common_refill_and_read_nolock@_W@@YAHV__crt_stdio_stream@@@Z`
- size: `417`
- prototype: `__int64 __fastcall(FILE *File)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400157a4`

## callees

- `0x1400046cc`
- `0x14000fa6c`
- `0x140011a0c`
- `0x140015498`
- `0x1400157ac`
- `0x14001899c`

## pseudocode

```c
__int64 __fastcall common_refill_and_read_nolock<wchar_t>(FILE *File)
{
  int base; // ebp
  unsigned __int8 v4; // r14
  char *v5; // rdi
  unsigned int charbuf; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rbx
  __int64 *v10; // rdx
  char *ptr; // rdx
  __int16 v12; // cx
  unsigned __int16 v13; // cx
  char *v14; // rdx

  if ( !File )
  {
    *(_DWORD *)sub_14000FA6C() = 22;
    invalid_parameter_noinfo();
    return 0xFFFF;
  }
  if ( (HIDWORD(File->_base) & 0x2000) == 0 || (HIDWORD(File->_base) & 0x1000) != 0 )
    return 0xFFFF;
  if ( (HIDWORD(File->_base) & 2) != 0 )
  {
    _InterlockedOr((volatile signed __int32 *)&File->_base + 1, 0x10u);
    return 0xFFFF;
  }
  _InterlockedOr((volatile signed __int32 *)&File->_base + 1, 1u);
  if ( (HIDWORD(File->_base) & 0x4C0) == 0 )
    _acrt_stdio_allocate_buffer_nolock();
  base = (int)File->_base;
  if ( base == 1 )
    v4 = *File->_ptr;
  else
    v4 = 0;
  v5 = *(char **)&File->_cnt;
  charbuf = File->_charbuf;
  File->_ptr = v5;
  v7 = fileno(File);
  v8 = read(v7, v5, charbuf);
  LODWORD(File->_base) = v8;
  if ( (unsigned int)(v8 + 1) <= 2 )
  {
    _InterlockedOr((volatile signed __int32 *)&File->_base + 1, v8 != 0 ? 16 : 8);
    LODWORD(File->_base) = 0;
    return 0xFFFF;
  }
  if ( (HIDWORD(File->_base) & 6) == 0 )
  {
    if ( fileno(File) == -1 || fileno(File) == -2 )
    {
      v10 = qword_1400D6230;
    }
    else
    {
      v9 = (__int64)fileno(File) >> 6;
      v10 = (__int64 *)(qword_1400D69C0[v9] + 72LL * (fileno(File) & 0x3F));
    }
    if ( (v10[7] & 0x82) == 0x82 )
      _InterlockedOr((volatile signed __int32 *)&File->_base + 1, 0x20u);
  }
  if ( File->_charbuf == 512 && (HIDWORD(File->_base) & 0x40) != 0 && (HIDWORD(File->_base) & 0x100) == 0 )
    File->_charbuf = 4096;
  ptr = File->_ptr;
  if ( base == 1 )
  {
    v12 = (unsigned __int8)*ptr;
    --LODWORD(File->_base);
    v13 = v4 | (unsigned __int16)(v12 << 8);
    v14 = ptr + 1;
  }
  else
  {
    v13 = *(_WORD *)ptr;
    LODWORD(File->_base) -= 2;
    v14 = ptr + 2;
  }
  File->_ptr = v14;
  return v13;
}

```

## disassembly

```asm
0x140015498  mov     rax, rsp
0x14001549b  mov     [rax+8], rbx
0x14001549f  mov     [rax+10h], rbp
0x1400154a3  mov     [rax+18h], rsi
0x1400154a7  mov     [rax+20h], rdi
0x1400154ab  push    r14
0x1400154ad  sub     rsp, 20h
0x1400154b1  mov     rsi, rcx
0x1400154b4  test    rcx, rcx
0x1400154b7  jnz     short loc_1400154E9
0x1400154b9  call    sub_14000FA6C
0x1400154be  mov     dword ptr [rax], 16h
0x1400154c4  call    _invalid_parameter_noinfo
0x1400154c9  mov     eax, 0FFFFh
0x1400154ce  mov     rbx, [rsp+28h+arg_0]
0x1400154d3  mov     rbp, [rsp+28h+arg_8]
0x1400154d8  mov     rsi, [rsp+28h+arg_10]
0x1400154dd  mov     rdi, [rsp+28h+arg_18]
0x1400154e2  add     rsp, 20h
0x1400154e6  pop     r14
0x1400154e8  retn
0x1400154e9  mov     eax, [rcx+14h]
0x1400154ec  nop
0x1400154ed  shr     eax, 0Dh
0x1400154f0  test    al, 1
0x1400154f2  jz      short loc_1400154C9
0x1400154f4  mov     eax, [rcx+14h]
0x1400154f7  nop
0x1400154f8  shr     eax, 0Ch
0x1400154fb  test    al, 1
0x1400154fd  jnz     short loc_1400154C9
0x1400154ff  mov     eax, [rcx+14h]
0x140015502  nop
0x140015503  shr     eax, 1
0x140015505  test    al, 1
0x140015507  jz      short loc_140015510
0x140015509  lock or dword ptr [rcx+14h], 10h
0x14001550e  jmp     short loc_1400154C9
0x140015510  lock or dword ptr [rcx+14h], 1
0x140015515  mov     eax, [rcx+14h]
0x140015518  nop
0x140015519  test    eax, 4C0h
0x14001551e  jnz     short loc_140015525
0x140015520  call    __acrt_stdio_allocate_buffer_nolock
0x140015525  mov     ebp, [rsi+10h]
0x140015528  cmp     ebp, 1
0x14001552b  jnz     short loc_140015535
0x14001552d  mov     rax, [rsi]
0x140015530  mov     r14b, [rax]
0x140015533  jmp     short loc_140015538
0x140015535  xor     r14b, r14b
0x140015538  mov     rdi, [rsi+8]
0x14001553c  mov     rcx, rsi; File
0x14001553f  mov     ebx, [rsi+20h]
0x140015542  mov     [rsi], rdi
0x140015545  call    _fileno
0x14001554a  mov     r8d, ebx; MaxCharCount
0x14001554d  mov     rdx, rdi; DstBuf
0x140015550  mov     ecx, eax; FileHandle
0x140015552  call    _read
0x140015557  mov     [rsi+10h], eax
0x14001555a  lea     ecx, [rax+1]
0x14001555d  cmp     ecx, 2
0x140015560  ja      short loc_140015579
0x140015562  neg     eax
0x140015564  sbb     eax, eax
0x140015566  and     eax, 8
0x140015569  add     eax, 8
0x14001556c  lock or [rsi+14h], eax
0x140015570  and     dword ptr [rsi+10h], 0
0x140015574  jmp     loc_1400154C9
0x140015579  mov     eax, [rsi+14h]
0x14001557c  nop
0x14001557d  test    al, 6
0x14001557f  jnz     short loc_1400155DF
0x140015581  mov     rcx, rsi; File
0x140015584  call    _fileno
0x140015589  cmp     eax, 0FFFFFFFFh
0x14001558c  jz      short loc_1400155CA
0x14001558e  mov     rcx, rsi; File
0x140015591  call    _fileno
0x140015596  cmp     eax, 0FFFFFFFEh
0x140015599  jz      short loc_1400155CA
0x14001559b  mov     rcx, rsi; File
0x14001559e  call    _fileno
0x1400155a3  movsxd  rbx, eax
0x1400155a6  lea     rdi, qword_1400D69C0
0x1400155ad  mov     rcx, rsi; File
0x1400155b0  sar     rbx, 6
0x1400155b4  call    _fileno
0x1400155b9  and     eax, 3Fh
0x1400155bc  lea     rdx, [rax+rax*8]
0x1400155c0  shl     rdx, 3
0x1400155c4  add     rdx, [rdi+rbx*8]
0x1400155c8  jmp     short loc_1400155D1
0x1400155ca  lea     rdx, qword_1400D6230
0x1400155d1  mov     al, [rdx+38h]
0x1400155d4  and     al, 82h
0x1400155d6  cmp     al, 82h
0x1400155d8  jnz     short loc_1400155DF
0x1400155da  lock or dword ptr [rsi+14h], 20h
0x1400155df  cmp     dword ptr [rsi+20h], 200h
0x1400155e6  jnz     short loc_140015605
0x1400155e8  mov     eax, [rsi+14h]
0x1400155eb  nop
0x1400155ec  shr     eax, 6
0x1400155ef  test    al, 1
0x1400155f1  jz      short loc_140015605
0x1400155f3  mov     eax, [rsi+14h]
0x1400155f6  nop
0x1400155f7  shr     eax, 8
0x1400155fa  test    al, 1
0x1400155fc  jnz     short loc_140015605
0x1400155fe  mov     dword ptr [rsi+20h], 1000h
0x140015605  mov     rdx, [rsi]
0x140015608  cmp     ebp, 1
0x14001560b  jnz     short loc_140015623
0x14001560d  movzx   ecx, byte ptr [rdx]
0x140015610  dec     dword ptr [rsi+10h]
0x140015613  shl     cx, 8
0x140015617  movzx   eax, r14b
0x14001561b  or      cx, ax
0x14001561e  inc     rdx
0x140015621  jmp     short loc_14001562E
0x140015623  movzx   ecx, word ptr [rdx]
0x140015626  add     dword ptr [rsi+10h], 0FFFFFFFEh
0x14001562a  add     rdx, 2
0x14001562e  mov     [rsi], rdx
0x140015631  movzx   eax, cx
0x140015634  jmp     loc_1400154CE
```
