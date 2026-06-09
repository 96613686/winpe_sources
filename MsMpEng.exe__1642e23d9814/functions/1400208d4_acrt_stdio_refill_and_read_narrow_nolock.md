# __acrt_stdio_refill_and_read_narrow_nolock

- ea: `0x1400208d4`
- end: `0x140020a3e`
- name: `__acrt_stdio_refill_and_read_narrow_nolock`
- size: `362`
- prototype: `__int64 __fastcall(FILE *File, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14001b8c4`

## callees

- `0x14001609c`
- `0x140016ea0`
- `0x14001b044`
- `0x1400208d4`
- `0x140020a48`
- `0x140023ffc`

## pseudocode

```c
__int64 __fastcall _acrt_stdio_refill_and_read_narrow_nolock(FILE *File, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned int v5; // edi
  char *v7; // rdi
  unsigned int charbuf; // ebx
  int v9; // eax
  int v10; // eax
  __int64 v11; // rbx
  __int64 *v12; // rax
  char *ptr; // rax

  if ( !File )
  {
    *(_DWORD *)sub_140016EA0(0, a2, a3, a4) = 22;
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
  v7 = *(char **)&File->_cnt;
  charbuf = File->_charbuf;
  File->_ptr = v7;
  v9 = fileno(File);
  v10 = read(v9, v7, charbuf);
  LODWORD(File->_base) = v10;
  if ( (unsigned int)(v10 + 1) <= 1 )
  {
    _InterlockedOr((volatile signed __int32 *)&File->_base + 1, v10 != 0 ? 16 : 8);
    LODWORD(File->_base) = 0;
    return (unsigned int)-1;
  }
  if ( (HIDWORD(File->_base) & 6) == 0 )
  {
    if ( fileno(File) == -1 || fileno(File) == -2 )
    {
      v12 = qword_14003CA30;
    }
    else
    {
      v11 = (__int64)fileno(File) >> 6;
      v12 = (__int64 *)(72LL * (fileno(File) & 0x3F) + qword_14003E600[v11]);
    }
    if ( (v12[7] & 0x82) == 0x82 )
      _InterlockedOr((volatile signed __int32 *)&File->_base + 1, 0x20u);
  }
  if ( File->_charbuf == 512 && (HIDWORD(File->_base) & 0x40) != 0 && (HIDWORD(File->_base) & 0x100) == 0 )
    File->_charbuf = 4096;
  ptr = File->_ptr;
  --LODWORD(File->_base);
  v5 = (unsigned __int8)*ptr;
  File->_ptr = ptr + 1;
  return v5;
}

```

## disassembly

```asm
0x1400208d4  mov     [rsp+arg_0], rbx
0x1400208d9  mov     [rsp+arg_8], rsi
0x1400208de  mov     [rsp+arg_10], rdi
0x1400208e3  push    r14
0x1400208e5  sub     rsp, 20h
0x1400208e9  mov     rsi, rcx
0x1400208ec  test    rcx, rcx
0x1400208ef  jnz     short loc_14002091C
0x1400208f1  call    sub_140016EA0
0x1400208f6  mov     dword ptr [rax], 16h
0x1400208fc  call    _invalid_parameter_noinfo
0x140020901  or      edi, 0FFFFFFFFh
0x140020904  mov     rbx, [rsp+28h+arg_0]
0x140020909  mov     eax, edi
0x14002090b  mov     rdi, [rsp+28h+arg_10]
0x140020910  mov     rsi, [rsp+28h+arg_8]
0x140020915  add     rsp, 20h
0x140020919  pop     r14
0x14002091b  retn
0x14002091c  mov     eax, [rcx+14h]
0x14002091f  nop
0x140020920  shr     eax, 0Dh
0x140020923  test    al, 1
0x140020925  jz      short loc_140020901
0x140020927  mov     eax, [rcx+14h]
0x14002092a  nop
0x14002092b  shr     eax, 0Ch
0x14002092e  test    al, 1
0x140020930  jnz     short loc_140020901
0x140020932  mov     eax, [rcx+14h]
0x140020935  nop
0x140020936  shr     eax, 1
0x140020938  test    al, 1
0x14002093a  jz      short loc_140020943
0x14002093c  lock or dword ptr [rcx+14h], 10h
0x140020941  jmp     short loc_140020901
0x140020943  lock or dword ptr [rcx+14h], 1
0x140020948  mov     eax, [rcx+14h]
0x14002094b  nop
0x14002094c  test    eax, 4C0h
0x140020951  jnz     short loc_140020958
0x140020953  call    __acrt_stdio_allocate_buffer_nolock
0x140020958  mov     rdi, [rsi+8]
0x14002095c  mov     rcx, rsi; File
0x14002095f  mov     ebx, [rsi+20h]
0x140020962  mov     [rsi], rdi
0x140020965  call    _fileno
0x14002096a  mov     r8d, ebx; MaxCharCount
0x14002096d  mov     rdx, rdi; DstBuf
0x140020970  mov     ecx, eax; FileHandle
0x140020972  call    _read
0x140020977  mov     [rsi+10h], eax
0x14002097a  lea     ecx, [rax+1]
0x14002097d  cmp     ecx, 1
0x140020980  ja      short loc_140020999
0x140020982  neg     eax
0x140020984  sbb     eax, eax
0x140020986  and     eax, 8
0x140020989  add     eax, 8
0x14002098c  lock or [rsi+14h], eax
0x140020990  and     dword ptr [rsi+10h], 0
0x140020994  jmp     loc_140020901
0x140020999  mov     eax, [rsi+14h]
0x14002099c  or      edi, 0FFFFFFFFh
0x14002099f  nop
0x1400209a0  test    al, 6
0x1400209a2  jnz     short loc_140020A04
0x1400209a4  mov     rcx, rsi; File
0x1400209a7  call    _fileno
0x1400209ac  cmp     eax, edi
0x1400209ae  jz      short loc_1400209EF
0x1400209b0  mov     rcx, rsi; File
0x1400209b3  call    _fileno
0x1400209b8  cmp     eax, 0FFFFFFFEh
0x1400209bb  jz      short loc_1400209EF
0x1400209bd  mov     rcx, rsi; File
0x1400209c0  call    _fileno
0x1400209c5  movsxd  rbx, eax
0x1400209c8  lea     r14, qword_14003E600
0x1400209cf  mov     rcx, rsi; File
0x1400209d2  sar     rbx, 6
0x1400209d6  call    _fileno
0x1400209db  and     eax, 3Fh
0x1400209de  lea     rcx, [rax+rax*8]
0x1400209e2  mov     rax, [r14+rbx*8]
0x1400209e6  shl     rcx, 3
0x1400209ea  add     rax, rcx
0x1400209ed  jmp     short loc_1400209F6
0x1400209ef  lea     rax, qword_14003CA30
0x1400209f6  mov     al, [rax+38h]
0x1400209f9  and     al, 82h
0x1400209fb  cmp     al, 82h
0x1400209fd  jnz     short loc_140020A04
0x1400209ff  lock or dword ptr [rsi+14h], 20h
0x140020a04  cmp     dword ptr [rsi+20h], 200h
0x140020a0b  jnz     short loc_140020A2A
0x140020a0d  mov     eax, [rsi+14h]
0x140020a10  nop
0x140020a11  shr     eax, 6
0x140020a14  test    al, 1
0x140020a16  jz      short loc_140020A2A
0x140020a18  mov     eax, [rsi+14h]
0x140020a1b  nop
0x140020a1c  shr     eax, 8
0x140020a1f  test    al, 1
0x140020a21  jnz     short loc_140020A2A
0x140020a23  mov     dword ptr [rsi+20h], 1000h
0x140020a2a  mov     rax, [rsi]
0x140020a2d  add     [rsi+10h], edi
0x140020a30  movzx   edi, byte ptr [rax]
0x140020a33  inc     rax
0x140020a36  mov     [rsi], rax
0x140020a39  jmp     loc_140020904
```
