# __acrt_stdio_refill_and_read_narrow_nolock

- ea: `0x14001563c`
- end: `0x1400157a3`
- name: `__acrt_stdio_refill_and_read_narrow_nolock`
- size: `359`
- prototype: `__int64 __fastcall(FILE *File, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140011bd4`

## callees

- `0x1400046cc`
- `0x14000fa6c`
- `0x140011a0c`
- `0x14001563c`
- `0x1400157ac`
- `0x14001899c`

## pseudocode

```c
__int64 __fastcall _acrt_stdio_refill_and_read_narrow_nolock(FILE *File, __int64 a2)
{
  unsigned int v3; // edi
  char *v5; // rdi
  unsigned int charbuf; // ebx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rbx
  __int64 *v10; // rdx
  char *ptr; // rax

  if ( !File )
  {
    *(_DWORD *)sub_14000FA6C(0, a2) = 22;
    invalid_parameter_noinfo();
    return (unsigned int)-1;
  }
  if ( (HIDWORD(File->_base) & 0x2000) == 0 || (HIDWORD(File->_base) & 0x1000) != 0 )
    return (unsigned int)-1;
  if ( (HIDWORD(File->_base) & 2) != 0 )
  {
    _InterlockedOr((volatile signed __int32 *)&File->_base + 1, 0x10u);
    return (unsigned int)-1;
  }
  _InterlockedOr((volatile signed __int32 *)&File->_base + 1, 1u);
  if ( (HIDWORD(File->_base) & 0x4C0) == 0 )
    _acrt_stdio_allocate_buffer_nolock();
  v5 = *(char **)&File->_cnt;
  charbuf = File->_charbuf;
  File->_ptr = v5;
  v7 = fileno(File);
  v8 = read(v7, v5, charbuf);
  LODWORD(File->_base) = v8;
  if ( (unsigned int)(v8 + 1) <= 1 )
  {
    _InterlockedOr((volatile signed __int32 *)&File->_base + 1, v8 != 0 ? 16 : 8);
    LODWORD(File->_base) = 0;
    return (unsigned int)-1;
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
  --LODWORD(File->_base);
  v3 = (unsigned __int8)*ptr;
  File->_ptr = ptr + 1;
  return v3;
}

```

## disassembly

```asm
0x14001563c  mov     [rsp+arg_0], rbx
0x140015641  mov     [rsp+arg_8], rsi
0x140015646  mov     [rsp+arg_10], rdi
0x14001564b  push    r14
0x14001564d  sub     rsp, 20h
0x140015651  mov     rsi, rcx
0x140015654  test    rcx, rcx
0x140015657  jnz     short loc_140015684
0x140015659  call    sub_14000FA6C
0x14001565e  mov     dword ptr [rax], 16h
0x140015664  call    _invalid_parameter_noinfo
0x140015669  or      edi, 0FFFFFFFFh
0x14001566c  mov     rbx, [rsp+28h+arg_0]
0x140015671  mov     eax, edi
0x140015673  mov     rdi, [rsp+28h+arg_10]
0x140015678  mov     rsi, [rsp+28h+arg_8]
0x14001567d  add     rsp, 20h
0x140015681  pop     r14
0x140015683  retn
0x140015684  mov     eax, [rcx+14h]
0x140015687  nop
0x140015688  shr     eax, 0Dh
0x14001568b  test    al, 1
0x14001568d  jz      short loc_140015669
0x14001568f  mov     eax, [rcx+14h]
0x140015692  nop
0x140015693  shr     eax, 0Ch
0x140015696  test    al, 1
0x140015698  jnz     short loc_140015669
0x14001569a  mov     eax, [rcx+14h]
0x14001569d  nop
0x14001569e  shr     eax, 1
0x1400156a0  test    al, 1
0x1400156a2  jz      short loc_1400156AB
0x1400156a4  lock or dword ptr [rcx+14h], 10h
0x1400156a9  jmp     short loc_140015669
0x1400156ab  lock or dword ptr [rcx+14h], 1
0x1400156b0  mov     eax, [rcx+14h]
0x1400156b3  nop
0x1400156b4  test    eax, 4C0h
0x1400156b9  jnz     short loc_1400156C0
0x1400156bb  call    __acrt_stdio_allocate_buffer_nolock
0x1400156c0  mov     rdi, [rsi+8]
0x1400156c4  mov     rcx, rsi; File
0x1400156c7  mov     ebx, [rsi+20h]
0x1400156ca  mov     [rsi], rdi
0x1400156cd  call    _fileno
0x1400156d2  mov     r8d, ebx; MaxCharCount
0x1400156d5  mov     rdx, rdi; DstBuf
0x1400156d8  mov     ecx, eax; FileHandle
0x1400156da  call    _read
0x1400156df  mov     [rsi+10h], eax
0x1400156e2  lea     ecx, [rax+1]
0x1400156e5  cmp     ecx, 1
0x1400156e8  ja      short loc_140015701
0x1400156ea  neg     eax
0x1400156ec  sbb     eax, eax
0x1400156ee  and     eax, 8
0x1400156f1  add     eax, 8
0x1400156f4  lock or [rsi+14h], eax
0x1400156f8  and     dword ptr [rsi+10h], 0
0x1400156fc  jmp     loc_140015669
0x140015701  mov     eax, [rsi+14h]
0x140015704  or      edi, 0FFFFFFFFh
0x140015707  nop
0x140015708  test    al, 6
0x14001570a  jnz     short loc_140015769
0x14001570c  mov     rcx, rsi; File
0x14001570f  call    _fileno
0x140015714  cmp     eax, edi
0x140015716  jz      short loc_140015754
0x140015718  mov     rcx, rsi; File
0x14001571b  call    _fileno
0x140015720  cmp     eax, 0FFFFFFFEh
0x140015723  jz      short loc_140015754
0x140015725  mov     rcx, rsi; File
0x140015728  call    _fileno
0x14001572d  movsxd  rbx, eax
0x140015730  lea     r14, qword_1400D69C0
0x140015737  mov     rcx, rsi; File
0x14001573a  sar     rbx, 6
0x14001573e  call    _fileno
0x140015743  and     eax, 3Fh
0x140015746  lea     rdx, [rax+rax*8]
0x14001574a  shl     rdx, 3
0x14001574e  add     rdx, [r14+rbx*8]
0x140015752  jmp     short loc_14001575B
0x140015754  lea     rdx, qword_1400D6230
0x14001575b  mov     al, [rdx+38h]
0x14001575e  and     al, 82h
0x140015760  cmp     al, 82h
0x140015762  jnz     short loc_140015769
0x140015764  lock or dword ptr [rsi+14h], 20h
0x140015769  cmp     dword ptr [rsi+20h], 200h
0x140015770  jnz     short loc_14001578F
0x140015772  mov     eax, [rsi+14h]
0x140015775  nop
0x140015776  shr     eax, 6
0x140015779  test    al, 1
0x14001577b  jz      short loc_14001578F
0x14001577d  mov     eax, [rsi+14h]
0x140015780  nop
0x140015781  shr     eax, 8
0x140015784  test    al, 1
0x140015786  jnz     short loc_14001578F
0x140015788  mov     dword ptr [rsi+20h], 1000h
0x14001578f  mov     rax, [rsi]
0x140015792  add     [rsi+10h], edi
0x140015795  movzx   edi, byte ptr [rax]
0x140015798  inc     rax
0x14001579b  mov     [rsi], rax
0x14001579e  jmp     loc_14001566C
```
