# common_refill_and_read_nolock<wchar_t>(__crt_stdio_stream)

- ea: `0x140020730`
- end: `0x1400208d4`
- name: `??$common_refill_and_read_nolock@_W@@YAHV__crt_stdio_stream@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(FILE *File)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140020a40`

## callees

- `0x14001609c`
- `0x140016ea0`
- `0x14001b044`
- `0x140020730`
- `0x140020a48`
- `0x140023ffc`

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
  __int64 *v10; // rax
  char *ptr; // rdx
  __int16 v12; // cx
  unsigned __int16 v13; // cx
  char *v14; // rdx

  if ( !File )
  {
    *(_DWORD *)sub_140016EA0() = 22;
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
      v10 = qword_14003CA30;
    }
    else
    {
      v9 = (__int64)fileno(File) >> 6;
      v10 = (__int64 *)(72LL * (fileno(File) & 0x3F) + qword_14003E600[v9]);
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
0x140020730  mov     rax, rsp
0x140020733  mov     [rax+8], rbx
0x140020737  mov     [rax+10h], rbp
0x14002073b  mov     [rax+18h], rsi
0x14002073f  mov     [rax+20h], rdi
0x140020743  push    r14
0x140020745  sub     rsp, 20h
0x140020749  mov     rsi, rcx
0x14002074c  test    rcx, rcx
0x14002074f  jnz     short loc_140020781
0x140020751  call    sub_140016EA0
0x140020756  mov     dword ptr [rax], 16h
0x14002075c  call    _invalid_parameter_noinfo
0x140020761  mov     eax, 0FFFFh
0x140020766  mov     rbx, [rsp+28h+arg_0]
0x14002076b  mov     rbp, [rsp+28h+arg_8]
0x140020770  mov     rsi, [rsp+28h+arg_10]
0x140020775  mov     rdi, [rsp+28h+arg_18]
0x14002077a  add     rsp, 20h
0x14002077e  pop     r14
0x140020780  retn
0x140020781  mov     eax, [rcx+14h]
0x140020784  nop
0x140020785  shr     eax, 0Dh
0x140020788  test    al, 1
0x14002078a  jz      short loc_140020761
0x14002078c  mov     eax, [rcx+14h]
0x14002078f  nop
0x140020790  shr     eax, 0Ch
0x140020793  test    al, 1
0x140020795  jnz     short loc_140020761
0x140020797  mov     eax, [rcx+14h]
0x14002079a  nop
0x14002079b  shr     eax, 1
0x14002079d  test    al, 1
0x14002079f  jz      short loc_1400207A8
0x1400207a1  lock or dword ptr [rcx+14h], 10h
0x1400207a6  jmp     short loc_140020761
0x1400207a8  lock or dword ptr [rcx+14h], 1
0x1400207ad  mov     eax, [rcx+14h]
0x1400207b0  nop
0x1400207b1  test    eax, 4C0h
0x1400207b6  jnz     short loc_1400207BD
0x1400207b8  call    __acrt_stdio_allocate_buffer_nolock
0x1400207bd  mov     ebp, [rsi+10h]
0x1400207c0  cmp     ebp, 1
0x1400207c3  jnz     short loc_1400207CD
0x1400207c5  mov     rax, [rsi]
0x1400207c8  mov     r14b, [rax]
0x1400207cb  jmp     short loc_1400207D0
0x1400207cd  xor     r14b, r14b
0x1400207d0  mov     rdi, [rsi+8]
0x1400207d4  mov     rcx, rsi; File
0x1400207d7  mov     ebx, [rsi+20h]
0x1400207da  mov     [rsi], rdi
0x1400207dd  call    _fileno
0x1400207e2  mov     r8d, ebx; MaxCharCount
0x1400207e5  mov     rdx, rdi; DstBuf
0x1400207e8  mov     ecx, eax; FileHandle
0x1400207ea  call    _read
0x1400207ef  mov     [rsi+10h], eax
0x1400207f2  lea     ecx, [rax+1]
0x1400207f5  cmp     ecx, 2
0x1400207f8  ja      short loc_140020811
0x1400207fa  neg     eax
0x1400207fc  sbb     eax, eax
0x1400207fe  and     eax, 8
0x140020801  add     eax, 8
0x140020804  lock or [rsi+14h], eax
0x140020808  and     dword ptr [rsi+10h], 0
0x14002080c  jmp     loc_140020761
0x140020811  mov     eax, [rsi+14h]
0x140020814  nop
0x140020815  test    al, 6
0x140020817  jnz     short loc_14002087A
0x140020819  mov     rcx, rsi; File
0x14002081c  call    _fileno
0x140020821  cmp     eax, 0FFFFFFFFh
0x140020824  jz      short loc_140020865
0x140020826  mov     rcx, rsi; File
0x140020829  call    _fileno
0x14002082e  cmp     eax, 0FFFFFFFEh
0x140020831  jz      short loc_140020865
0x140020833  mov     rcx, rsi; File
0x140020836  call    _fileno
0x14002083b  movsxd  rbx, eax
0x14002083e  lea     rdi, qword_14003E600
0x140020845  mov     rcx, rsi; File
0x140020848  sar     rbx, 6
0x14002084c  call    _fileno
0x140020851  and     eax, 3Fh
0x140020854  lea     rcx, [rax+rax*8]
0x140020858  mov     rax, [rdi+rbx*8]
0x14002085c  shl     rcx, 3
0x140020860  add     rax, rcx
0x140020863  jmp     short loc_14002086C
0x140020865  lea     rax, qword_14003CA30
0x14002086c  mov     al, [rax+38h]
0x14002086f  and     al, 82h
0x140020871  cmp     al, 82h
0x140020873  jnz     short loc_14002087A
0x140020875  lock or dword ptr [rsi+14h], 20h
0x14002087a  cmp     dword ptr [rsi+20h], 200h
0x140020881  jnz     short loc_1400208A0
0x140020883  mov     eax, [rsi+14h]
0x140020886  nop
0x140020887  shr     eax, 6
0x14002088a  test    al, 1
0x14002088c  jz      short loc_1400208A0
0x14002088e  mov     eax, [rsi+14h]
0x140020891  nop
0x140020892  shr     eax, 8
0x140020895  test    al, 1
0x140020897  jnz     short loc_1400208A0
0x140020899  mov     dword ptr [rsi+20h], 1000h
0x1400208a0  mov     rdx, [rsi]
0x1400208a3  cmp     ebp, 1
0x1400208a6  jnz     short loc_1400208BE
0x1400208a8  movzx   ecx, byte ptr [rdx]
0x1400208ab  dec     dword ptr [rsi+10h]
0x1400208ae  shl     cx, 8
0x1400208b2  movzx   eax, r14b
0x1400208b6  or      cx, ax
0x1400208b9  inc     rdx
0x1400208bc  jmp     short loc_1400208C9
0x1400208be  movzx   ecx, word ptr [rdx]
0x1400208c1  add     dword ptr [rsi+10h], 0FFFFFFFEh
0x1400208c5  add     rdx, 2
0x1400208c9  mov     [rsi], rdx
0x1400208cc  movzx   eax, cx
0x1400208cf  jmp     loc_140020766
```
