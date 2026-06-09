# CPersistErrorCache::GetErrorDescription(long,ulong)

- ea: `0x18001616c`
- end: `0x18001655d`
- name: `?GetErrorDescription@CPersistErrorCache@@AEAAPEAGJK@Z`
- size: `1009`
- prototype: `unsigned __int16 *(CPersistErrorCache *__hidden this, int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180015b78`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x1800027c0`
- `0x18001616c`
- `0x18001676c`
- `0x1800167e4`
- `0x180016bf4`
- `0x18001a6c8`
- `0x18002cd54`

## import_xrefs

- `msvcrt!wcsstr` at `0x180016352`
- `msvcrt!wcsstr` at `0x180016352`

## pseudocode

```c
unsigned __int8 *__fastcall CPersistErrorCache::GetErrorDescription(CPersistErrorCache *this, unsigned int a2, UINT a3)
{
  UINT v3; // ebx
  CPersistErrorCache *v4; // r15
  unsigned __int8 *v5; // rsi
  unsigned int v6; // edx
  CPersistErrorCache *v7; // rcx
  unsigned __int8 *v8; // r14
  CPersistErrorCache *v9; // rcx
  wchar_t *v10; // r13
  unsigned int v11; // r12d
  __int64 v12; // rbx
  wchar_t *v13; // rax
  wchar_t *v14; // r15
  __int64 v15; // rcx
  __int64 v16; // r9
  int v17; // eax
  int v18; // r15d
  unsigned __int16 *v19; // r8
  __int64 v20; // rax
  unsigned int v21; // ebx
  unsigned int v23; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int8 *v24; // [rsp+38h] [rbp-50h]
  unsigned __int8 *v25; // [rsp+40h] [rbp-48h]
  unsigned int v27; // [rsp+A0h] [rbp+18h] BYREF
  unsigned int v28; // [rsp+A8h] [rbp+20h] BYREF

  v3 = a3;
  v4 = this;
  if ( !a3 )
  {
    switch ( a2 )
    {
      case 0x80040E00:
        v3 = 113;
        break;
      case 0x80040E21:
        v3 = 114;
        break;
      case 0x80040E55:
        v3 = 115;
        break;
      case 0x80040E5C:
        v3 = 116;
        break;
      case 0x80040E23:
        v3 = 117;
        break;
      case 0x80040E24:
        v3 = 118;
        break;
      case 0x80040E25:
        v3 = 119;
        break;
      case 0x80040E04:
        v3 = 120;
        break;
      case 0x80040E35:
        v3 = 121;
        break;
      case 0x80040E07:
        v3 = 122;
        break;
      case 0x80040E22:
        v3 = 123;
        break;
      case 0x80040E37:
        v3 = 124;
        break;
      case 0x80070057:
        v3 = 125;
        break;
      case 0x80004001:
        v3 = 127;
        break;
      case 0x80030103:
        v3 = 129;
        break;
      case 0x80030002:
        v3 = 130;
        break;
      case 0x40EC6u:
        v3 = 131;
        break;
      case 0x40EC0u:
        v3 = 132;
        break;
      case 0x80004005:
        v3 = 135;
        break;
      default:
        return 0;
    }
  }
  v24 = 0;
  v5 = MMMAlloc(0x800u, a2);
  v25 = v5;
  OnNullThrowOOM(v5);
  try
  {
    *((_WORD *)v5 + 1023) = 0;
    if ( !*((_DWORD *)v4 + 4) )
    {
      CPersistErrorCache::LoadDescription(v7, v3, (unsigned __int16 *)v5);
      return v5;
    }
    v8 = MMMAlloc(0x800u, v6);
    v24 = v8;
    OnNullThrowOOM(v8);
    CPersistErrorCache::LoadDescription(v9, v3, (unsigned __int16 *)v8);
    v27 = 0;
    v10 = (wchar_t *)v8;
    v11 = 0;
    v12 = -1;
    while ( v11 < *((_DWORD *)v4 + 4) )
    {
      v13 = wcsstr(v10, L"%p%");
      v14 = v13;
      if ( !v13 )
        break;
      v28 = v13 - v10;
      InsertString(&v28, &v27, v10, (unsigned __int16 *)v5);
      v10 = v14 + 3;
      LODWORD(v15) = v27;
      if ( v27 >= 0x3FF )
        break;
      v4 = this;
      v16 = *((_QWORD *)this + 3);
      if ( *(_WORD *)(v16 + 24LL * v11) == 19 )
      {
        v17 = StringCchPrintfW(
                (unsigned __int16 *)&v5[2 * v27],
                1024 - v27,
                L"%u",
                *(unsigned int *)(v16 + 24LL * v11 + 8));
        v18 = v17;
        if ( v17 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048A18[0] )
            bidTraceW(off_1800481E8[0], 681984, off_180048A18[0], (unsigned int)v17, 666);
          ThrowHR(v18);
        }
        v15 = -1;
        do
          ++v15;
        while ( *(_WORD *)&v5[2 * v15] );
        v27 = v15;
        v4 = this;
      }
      else
      {
        if ( *(_WORD *)(v16 + 24LL * v11) == 8 )
        {
          v19 = *(unsigned __int16 **)(v16 + 24LL * v11 + 8);
          if ( !v19 )
            goto LABEL_63;
          v20 = -1;
          do
            ++v20;
          while ( v19[v20] );
          v28 = v20;
        }
        else
        {
          v28 = 3;
          v19 = L"???";
        }
        InsertString(&v28, &v27, v19, (unsigned __int16 *)v5);
        LODWORD(v15) = v27;
      }
LABEL_63:
      if ( (unsigned int)v15 >= 0x3FF )
        goto LABEL_65;
      ++v11;
    }
    do
LABEL_65:
      ++v12;
    while ( v10[v12] );
    v28 = v12;
    InsertString(&v28, &v27, v10, (unsigned __int16 *)v5);
    *(_WORD *)&v5[2 * v27] = 0;
    if ( v8 )
      MMMFree(v8);
  }
  catch ( long v23 )
  {
    v27 = v23;
    if ( v25 )
      MMMFree(v25);
    if ( v24 )
      MMMFree(v24);
    v21 = v27;
    if ( (v27 & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048A10[0] )
          bidTraceW(off_1800481E8[0], 740352, off_180048A10[0], v27, 723);
      }
      ThrowHR(v21);
    }
    return v25;
  }
  return v5;
}

```

## disassembly

```asm
0x18001616c  mov     [rsp+arg_0], rcx
0x180016171  push    rbx
0x180016172  push    rsi
0x180016173  push    rdi
0x180016174  push    r12
0x180016176  push    r13
0x180016178  push    r14
0x18001617a  push    r15
0x18001617c  sub     rsp, 50h
0x180016180  mov     ebx, r8d
0x180016183  mov     r15, rcx
0x180016186  xor     edi, edi
0x180016188  test    r8d, r8d
0x18001618b  jnz     loc_1800162CC
0x180016191  cmp     edx, 80040E00h
0x180016197  jnz     short loc_1800161A1
0x180016199  lea     ebx, [rdi+71h]
0x18001619c  jmp     loc_1800162CC
0x1800161a1  cmp     edx, 80040E21h
0x1800161a7  jnz     short loc_1800161B3
0x1800161a9  mov     ebx, 72h ; 'r'
0x1800161ae  jmp     loc_1800162CC
0x1800161b3  cmp     edx, 80040E55h
0x1800161b9  jnz     short loc_1800161C5
0x1800161bb  mov     ebx, 73h ; 's'
0x1800161c0  jmp     loc_1800162CC
0x1800161c5  cmp     edx, 80040E5Ch
0x1800161cb  jnz     short loc_1800161D7
0x1800161cd  mov     ebx, 74h ; 't'
0x1800161d2  jmp     loc_1800162CC
0x1800161d7  cmp     edx, 80040E23h
0x1800161dd  jnz     short loc_1800161E9
0x1800161df  mov     ebx, 75h ; 'u'
0x1800161e4  jmp     loc_1800162CC
0x1800161e9  cmp     edx, 80040E24h
0x1800161ef  jnz     short loc_1800161FB
0x1800161f1  mov     ebx, 76h ; 'v'
0x1800161f6  jmp     loc_1800162CC
0x1800161fb  cmp     edx, 80040E25h
0x180016201  jnz     short loc_18001620D
0x180016203  mov     ebx, 77h ; 'w'
0x180016208  jmp     loc_1800162CC
0x18001620d  cmp     edx, 80040E04h
0x180016213  jnz     short loc_18001621F
0x180016215  mov     ebx, 78h ; 'x'
0x18001621a  jmp     loc_1800162CC
0x18001621f  cmp     edx, 80040E35h
0x180016225  jnz     short loc_180016231
0x180016227  mov     ebx, 79h ; 'y'
0x18001622c  jmp     loc_1800162CC
0x180016231  cmp     edx, 80040E07h
0x180016237  jnz     short loc_180016243
0x180016239  mov     ebx, 7Ah ; 'z'
0x18001623e  jmp     loc_1800162CC
0x180016243  cmp     edx, 80040E22h
0x180016249  jnz     short loc_180016252
0x18001624b  mov     ebx, 7Bh ; '{'
0x180016250  jmp     short loc_1800162CC
0x180016252  cmp     edx, 80040E37h
0x180016258  jnz     short loc_180016261
0x18001625a  mov     ebx, 7Ch ; '|'
0x18001625f  jmp     short loc_1800162CC
0x180016261  cmp     edx, 80070057h
0x180016267  jnz     short loc_180016270
0x180016269  mov     ebx, 7Dh ; '}'
0x18001626e  jmp     short loc_1800162CC
0x180016270  cmp     edx, 80004001h
0x180016276  jnz     short loc_18001627F
0x180016278  mov     ebx, 7Fh
0x18001627d  jmp     short loc_1800162CC
0x18001627f  cmp     edx, 80030103h
0x180016285  jnz     short loc_18001628E
0x180016287  mov     ebx, 81h
0x18001628c  jmp     short loc_1800162CC
0x18001628e  cmp     edx, 80030002h
0x180016294  jnz     short loc_18001629D
0x180016296  mov     ebx, 82h
0x18001629b  jmp     short loc_1800162CC
0x18001629d  cmp     edx, 40EC6h
0x1800162a3  jnz     short loc_1800162AC
0x1800162a5  mov     ebx, 83h
0x1800162aa  jmp     short loc_1800162CC
0x1800162ac  cmp     edx, 40EC0h
0x1800162b2  jnz     short loc_1800162BB
0x1800162b4  mov     ebx, 84h
0x1800162b9  jmp     short loc_1800162CC
0x1800162bb  cmp     edx, 80004005h
0x1800162c1  jnz     loc_18001654B
0x1800162c7  mov     ebx, 87h
0x1800162cc  mov     [rsp+88h+var_50], rdi
0x1800162d1  mov     r14d, 800h
0x1800162d7  mov     ecx, r14d; unsigned int
0x1800162da  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x1800162df  mov     rsi, rax
0x1800162e2  mov     [rsp+88h+var_48], rax
0x1800162e7  mov     rcx, rax; void *
0x1800162ea  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x1800162ef  mov     [rsi+7FEh], di
0x1800162f6  cmp     [r15+10h], edi
0x1800162fa  jnz     short loc_18001630B
0x1800162fc  mov     r8, rsi; unsigned __int16 *
0x1800162ff  mov     edx, ebx; unsigned int
0x180016301  call    ?LoadDescription@CPersistErrorCache@@AEAAXKPEAGK@Z; CPersistErrorCache::LoadDescription(ulong,ushort *,ulong)
0x180016306  jmp     loc_1800164F4
0x18001630b  mov     ecx, r14d; unsigned int
0x18001630e  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180016313  mov     r14, rax
0x180016316  mov     [rsp+88h+var_50], rax
0x18001631b  mov     rcx, rax; void *
0x18001631e  call    ?OnNullThrowOOM@@YAXPEAX@Z; OnNullThrowOOM(void *)
0x180016323  mov     r8, r14; unsigned __int16 *
0x180016326  mov     edx, ebx; unsigned int
0x180016328  call    ?LoadDescription@CPersistErrorCache@@AEAAXKPEAGK@Z; CPersistErrorCache::LoadDescription(ulong,ushort *,ulong)
0x18001632d  mov     [rsp+88h+arg_10], edi
0x180016334  mov     r13, r14
0x180016337  mov     r12d, edi
0x18001633a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001633e  cmp     r12d, [r15+10h]
0x180016342  jnb     loc_1800164AE
0x180016348  lea     rdx, aP; "%p%"
0x18001634f  mov     rcx, r13; Str
0x180016352  call    cs:__imp_wcsstr
0x180016358  mov     r15, rax
0x18001635b  test    rax, rax
0x18001635e  jz      loc_1800164AE
0x180016364  mov     rcx, rax
0x180016367  sub     rcx, r13
0x18001636a  sar     rcx, 1
0x18001636d  mov     [rsp+88h+arg_18], ecx
0x180016374  mov     r9, rsi; unsigned __int16 *
0x180016377  mov     r8, r13; unsigned __int16 *
0x18001637a  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x180016382  lea     rcx, [rsp+88h+arg_18]; unsigned int *
0x18001638a  call    ?InsertString@@YAXPEAK0PEAG1@Z; InsertString(ulong *,ulong *,ushort *,ushort *)
0x18001638f  lea     r13, [r15+6]
0x180016393  mov     ecx, [rsp+88h+arg_10]
0x18001639a  cmp     ecx, 3FFh
0x1800163a0  jnb     loc_1800164AE
0x1800163a6  mov     eax, r12d
0x1800163a9  lea     r8, [rax+rax*2]
0x1800163ad  mov     r15, [rsp+88h+arg_0]
0x1800163b5  mov     r9, [r15+18h]
0x1800163b9  cmp     word ptr [r9+r8*8], 13h
0x1800163bf  jnz     loc_180016445
0x1800163c5  mov     edx, 400h
0x1800163ca  sub     edx, ecx; unsigned __int64
0x1800163cc  lea     rcx, [rsi+rcx*2]; unsigned __int16 *
0x1800163d0  mov     r9d, [r9+r8*8+8]
0x1800163d5  lea     r8, aU; "%u"
0x1800163dc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800163e1  mov     r15d, eax
0x1800163e4  test    eax, eax
0x1800163e6  jns     short loc_180016428
0x1800163e8  test    byte ptr cs:_bidGblFlags, 2
0x1800163ef  jz      short loc_180016420
0x1800163f1  mov     rcx, cs:off_180048A18; "<CPersistErrorCache::GetErrorDescriptio"...
0x1800163f8  test    rcx, rcx
0x1800163fb  jz      short loc_180016420
0x1800163fd  mov     [rsp+88h+var_68], 29Ah
0x180016405  mov     r9d, eax
0x180016408  mov     r8, cs:off_180048A18; "<CPersistErrorCache::GetErrorDescriptio"...
0x18001640f  mov     edx, 0A6800h
0x180016414  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001641b  call    _bidTraceW
0x180016420  mov     ecx, r15d; int
0x180016423  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016428  mov     rcx, rbx
0x18001642b  inc     rcx
0x18001642e  cmp     [rsi+rcx*2], di
0x180016432  jnz     short loc_18001642B
0x180016434  mov     [rsp+88h+arg_10], ecx
0x18001643b  mov     r15, [rsp+88h+arg_0]
0x180016443  jmp     short loc_18001649E
0x180016445  cmp     word ptr [r9+r8*8], 8
0x18001644b  jnz     short loc_18001646D
0x18001644d  mov     r8, [r9+r8*8+8]
0x180016452  test    r8, r8
0x180016455  jz      short loc_18001649E
0x180016457  mov     rax, rbx
0x18001645a  inc     rax
0x18001645d  cmp     [r8+rax*2], di
0x180016462  jnz     short loc_18001645A
0x180016464  mov     [rsp+88h+arg_18], eax
0x18001646b  jmp     short loc_18001647F
0x18001646d  mov     [rsp+88h+arg_18], 3
0x180016478  lea     r8, asc_180038890; "???"
0x18001647f  mov     r9, rsi; unsigned __int16 *
0x180016482  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x18001648a  lea     rcx, [rsp+88h+arg_18]; unsigned int *
0x180016492  call    ?InsertString@@YAXPEAK0PEAG1@Z; InsertString(ulong *,ulong *,ushort *,ushort *)
0x180016497  mov     ecx, [rsp+88h+arg_10]
0x18001649e  cmp     ecx, 3FFh
0x1800164a4  jnb     short loc_1800164AE
0x1800164a6  inc     r12d
0x1800164a9  jmp     loc_18001633E
0x1800164ae  inc     rbx
0x1800164b1  cmp     [r13+rbx*2+0], di
0x1800164b7  jnz     short loc_1800164AE
0x1800164b9  mov     [rsp+88h+arg_18], ebx
0x1800164c0  mov     r9, rsi; unsigned __int16 *
0x1800164c3  mov     r8, r13; unsigned __int16 *
0x1800164c6  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x1800164ce  lea     rcx, [rsp+88h+arg_18]; unsigned int *
0x1800164d6  call    ?InsertString@@YAXPEAK0PEAG1@Z; InsertString(ulong *,ulong *,ushort *,ushort *)
0x1800164db  mov     eax, [rsp+88h+arg_10]
0x1800164e2  mov     [rsi+rax*2], di
0x1800164e6  test    r14, r14
0x1800164e9  jz      short loc_1800164F4
0x1800164eb  mov     rcx, r14; unsigned __int8 *
0x1800164ee  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x1800164f3  nop
0x1800164f4  jmp     short loc_180016546
0x1800164f6  mov     ebx, [rsp+88h+arg_10]
0x1800164fd  test    ebx, ebx
0x1800164ff  jns     short loc_180016541
0x180016501  test    byte ptr cs:_bidGblFlags, 2
0x180016508  jz      short loc_180016539
0x18001650a  mov     rax, cs:off_180048A10; "<CPersistErrorCache::GetErrorDescriptio"...
0x180016511  test    rax, rax
0x180016514  jz      short loc_180016539
0x180016516  mov     [rsp+88h+var_68], 2D3h
0x18001651e  mov     r9d, ebx
0x180016521  mov     r8, cs:off_180048A10; "<CPersistErrorCache::GetErrorDescriptio"...
0x180016528  mov     edx, 0B4C00h
0x18001652d  mov     rcx, cs:off_1800481E8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180016534  call    _bidTraceW
0x180016539  mov     ecx, ebx; int
0x18001653b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180016541  mov     rsi, [rsp+88h+var_48]
0x180016546  mov     rax, rsi
0x180016549  jmp     short loc_18001654D
0x18001654b  xor     eax, eax
0x18001654d  add     rsp, 50h
0x180016551  pop     r15
0x180016553  pop     r14
0x180016555  pop     r13
0x180016557  pop     r12
0x180016559  pop     rdi
0x18001655a  pop     rsi
0x18001655b  pop     rbx
0x18001655c  retn
```
