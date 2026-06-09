# COMMAND_PROCESSOR::GetConfigSystem(ushort const *,INativeConfigurationSystem * *)

- ea: `0x1800082d0`
- end: `0x180008594`
- name: `?GetConfigSystem@COMMAND_PROCESSOR@@UEAAJPEBGPEAPEAVINativeConfigurationSystem@@@Z`
- size: `708`
- prototype: `__int64 __fastcall(COMMAND_PROCESSOR *__hidden this, const unsigned __int16 *, struct INativeConfigurationSystem **)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x1800049b0`
- `0x180005d74`
- `0x180006960`
- `0x180006e00`
- `0x180006f0c`
- `0x1800082d0`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800083ef`
- `msvcrt!_wcsicmp` at `0x1800083ef`

## pseudocode

```c
__int64 __fastcall COMMAND_PROCESSOR::GetConfigSystem(
        COMMAND_PROCESSOR *this,
        const unsigned __int8 *a2,
        struct INativeConfigurationSystem **a3)
{
  int v5; // ebx
  unsigned int v6; // edx
  struct IArrayListEntry *v7; // rsi
  struct INativeConfigurationSystem *v8; // rdi
  wchar_t *v9; // r10
  unsigned int i; // r15d
  __int64 v11; // rdi
  int v12; // eax
  struct IArrayListEntry *v13; // rax
  struct INativeConfigurationSystem *v15; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v16[4]; // [rsp+38h] [rbp-51h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-31h]
  int v18; // [rsp+60h] [rbp-29h]
  __int16 v19; // [rsp+64h] [rbp-25h]
  unsigned int v20; // [rsp+68h] [rbp-21h]
  _QWORD v21[5]; // [rsp+70h] [rbp-19h] BYREF
  int v22; // [rsp+98h] [rbp+Fh]
  __int16 v23; // [rsp+9Ch] [rbp+13h]
  int v24; // [rsp+A0h] [rbp+17h]

  v19 = 256;
  v15 = 0;
  String1 = (wchar_t *)v16;
  v16[0] = 0;
  v20 = 0;
  v18 = 32;
  v22 = 32;
  v21[0] = 0;
  v21[4] = v21;
  v23 = 256;
  v24 = 0;
  if ( !a3 )
  {
    v5 = -2147024809;
    goto LABEL_32;
  }
  v5 = STRU::Copy((STRU *)v16, a2);
  if ( v5 < 0 )
    goto LABEL_32;
  v6 = v20;
  v7 = 0;
  if ( !v20 )
  {
    v5 = NATIVE_READER::CreateReadOnlyConfigSystem(
           *((_DWORD *)this + 47),
           *((OLECHAR **)this + 13),
           *((const unsigned __int16 **)this + 20),
           &v15);
    if ( v5 >= 0 )
    {
      v8 = v15;
      goto LABEL_24;
    }
LABEL_27:
    v8 = v15;
    goto LABEL_28;
  }
  while ( 1 )
  {
    v9 = String1;
    if ( v6 <= 1 || String1[v6 - 1] != 47 )
      break;
    if ( !STRU::SetLen((STRU *)v16, v6 - 1) )
    {
      v5 = -2147024774;
      goto LABEL_32;
    }
    v6 = v20;
  }
  for ( i = 0; i < *((_DWORD *)this + 80); ++i )
  {
    v11 = *(_QWORD *)(*((_QWORD *)this + 39) + 8LL * i);
    if ( !v11 )
    {
      v5 = -2147024883;
      goto LABEL_32;
    }
    v12 = _wcsicmp(v9, *(const wchar_t **)(v11 + 48));
    if ( !v12 )
    {
      v8 = *(struct INativeConfigurationSystem **)(v11 + 8);
      (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v8 + 8LL))(v8);
      goto LABEL_24;
    }
    v9 = String1;
    if ( v12 > 0 )
      break;
  }
  v5 = NATIVE_READER::CreateWritableConfigSystem(
         *((_DWORD *)this + 47),
         v9,
         *((OLECHAR **)this + 13),
         *((const unsigned __int16 **)this + 20),
         &v15);
  if ( v5 < 0 )
    goto LABEL_27;
  v13 = (struct IArrayListEntry *)operator new(0xC0u);
  v8 = v15;
  v7 = v13;
  if ( !v13 )
  {
    v5 = -2147024888;
    goto LABEL_25;
  }
  *((_QWORD *)v13 + 1) = 0;
  *(_QWORD *)v13 = &CONFIG_SYSTEM_ENTRY::`vftable';
  *((_DWORD *)v13 + 14) = 32;
  *((_QWORD *)v13 + 2) = 0;
  *((_QWORD *)v13 + 6) = (char *)v13 + 16;
  *((_WORD *)v13 + 30) = 256;
  *((_DWORD *)v13 + 16) = 0;
  *((_DWORD *)v13 + 28) = 32;
  *((_QWORD *)v13 + 9) = 0;
  *((_QWORD *)v13 + 13) = (char *)v13 + 72;
  *((_WORD *)v13 + 58) = 256;
  *((_DWORD *)v13 + 30) = 0;
  *((_DWORD *)v13 + 42) = 32;
  *((_QWORD *)v13 + 16) = 0;
  *((_QWORD *)v13 + 20) = (char *)v13 + 128;
  *((_WORD *)v13 + 86) = 256;
  *((_DWORD *)v13 + 44) = 0;
  *((_QWORD *)v13 + 23) = 0;
  v5 = CONFIG_SYSTEM_ENTRY::Create(
         v13,
         v8,
         *((_DWORD *)this + 47),
         (const unsigned __int8 *)String1,
         *((unsigned __int16 **)this + 13),
         *((unsigned __int16 **)this + 20));
  if ( v5 < 0 )
    goto LABEL_28;
  v5 = ARRAY_LIST::AddEntry((COMMAND_PROCESSOR *)((char *)this + 312), v7, i);
  if ( v5 < 0 )
    goto LABEL_28;
LABEL_24:
  *a3 = v8;
  v8 = 0;
LABEL_25:
  v7 = 0;
LABEL_28:
  if ( v8 )
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v7 )
    (**(void (__fastcall ***)(struct IArrayListEntry *))v7)(v7);
LABEL_32:
  BUFFER::~BUFFER((BUFFER *)v21);
  BUFFER::~BUFFER((BUFFER *)v16);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800082d0  mov     [rsp-8+arg_18], rbx
0x1800082d5  push    rbp
0x1800082d6  push    rsi
0x1800082d7  push    rdi
0x1800082d8  push    r12
0x1800082da  push    r13
0x1800082dc  push    r14
0x1800082de  push    r15
0x1800082e0  lea     rbp, [rsp-27h]
0x1800082e5  sub     rsp, 0B0h
0x1800082ec  mov     rax, cs:__security_cookie
0x1800082f3  xor     rax, rsp
0x1800082f6  mov     [rbp+57h+var_38], rax
0x1800082fa  xor     r13d, r13d
0x1800082fd  mov     [rbp+57h+var_7C], 100h
0x180008303  mov     [rbp+57h+var_B0], r13
0x180008307  lea     rax, [rbp+57h+var_A8]
0x18000830b  mov     [rbp+57h+String1], rax
0x18000830f  lea     rax, [rbp+57h+var_70]
0x180008313  mov     [rbp+57h+var_A8], r13
0x180008317  mov     r12, r8
0x18000831a  mov     [rbp+57h+var_78], r13d
0x18000831e  lea     edi, [r13+20h]
0x180008322  mov     [rbp+57h+var_80], edi
0x180008325  mov     r14, rcx
0x180008328  mov     [rbp+57h+var_48], edi
0x18000832b  mov     [rbp+57h+var_70], r13
0x18000832f  mov     [rbp+57h+var_50], rax
0x180008333  mov     [rbp+57h+var_44], 100h
0x180008339  mov     [rbp+57h+var_40], r13d
0x18000833d  test    r8, r8
0x180008340  jnz     short loc_18000834C
0x180008342  mov     ebx, 80070057h
0x180008347  jmp     loc_180008559
0x18000834c  lea     rcx, [rbp+57h+var_A8]; this
0x180008350  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180008355  mov     ebx, eax
0x180008357  test    eax, eax
0x180008359  js      loc_180008559
0x18000835f  mov     edx, [rbp+57h+var_78]
0x180008362  mov     rsi, r13
0x180008365  test    edx, edx
0x180008367  jnz     short loc_180008397
0x180008369  mov     r8, [r14+0A0h]; unsigned __int16 *
0x180008370  lea     r9, [rbp+57h+var_B0]; struct INativeConfigurationSystem **
0x180008374  mov     rdx, [r14+68h]; unsigned __int16 *
0x180008378  mov     ecx, [r14+0BCh]; int
0x18000837f  call    ?CreateReadOnlyConfigSystem@NATIVE_READER@@SAJHPEBG0PEAPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::CreateReadOnlyConfigSystem(int,ushort const *,ushort const *,INativeConfigurationSystem * *)
0x180008384  mov     ebx, eax
0x180008386  test    eax, eax
0x180008388  js      loc_18000852E
0x18000838e  mov     rdi, [rbp+57h+var_B0]
0x180008392  jmp     loc_18000851B
0x180008397  mov     r10, [rbp+57h+String1]
0x18000839b  cmp     edx, 1
0x18000839e  jbe     short loc_1800083C9
0x1800083a0  lea     eax, [rdx-1]
0x1800083a3  cmp     word ptr [r10+rax*2], 2Fh ; '/'
0x1800083a9  jnz     short loc_1800083C9
0x1800083ab  dec     edx; unsigned int
0x1800083ad  lea     rcx, [rbp+57h+var_A8]; this
0x1800083b1  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x1800083b6  test    al, al
0x1800083b8  jz      short loc_1800083BF
0x1800083ba  mov     edx, [rbp+57h+var_78]
0x1800083bd  jmp     short loc_180008397
0x1800083bf  mov     ebx, 8007007Ah
0x1800083c4  jmp     loc_180008559
0x1800083c9  mov     r15d, r13d
0x1800083cc  cmp     r15d, [r14+140h]
0x1800083d3  jnb     short loc_180008426
0x1800083d5  mov     rax, [r14+138h]
0x1800083dc  mov     edx, r15d
0x1800083df  mov     rdi, [rax+rdx*8]
0x1800083e3  test    rdi, rdi
0x1800083e6  jz      short loc_18000841C
0x1800083e8  mov     rdx, [rdi+30h]; String2
0x1800083ec  mov     rcx, r10; String1
0x1800083ef  call    cs:__imp__wcsicmp
0x1800083f5  test    eax, eax
0x1800083f7  jz      short loc_180008404
0x1800083f9  mov     r10, [rbp+57h+String1]
0x1800083fd  jg      short loc_180008426
0x1800083ff  inc     r15d
0x180008402  jmp     short loc_1800083CC
0x180008404  mov     rdi, [rdi+8]
0x180008408  mov     rcx, rdi
0x18000840b  mov     rax, [rdi]
0x18000840e  mov     rax, [rax+8]
0x180008412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008417  jmp     loc_18000851B
0x18000841c  mov     ebx, 8007000Dh
0x180008421  jmp     loc_180008559
0x180008426  mov     r9, [r14+0A0h]; unsigned __int16 *
0x18000842d  lea     rax, [rbp+57h+var_B0]
0x180008431  mov     r8, [r14+68h]; unsigned __int16 *
0x180008435  mov     rdx, r10; unsigned __int16 *
0x180008438  mov     ecx, [r14+0BCh]; int
0x18000843f  mov     [rsp+0E0h+var_C0], rax; struct INativeConfigurationSystem **
0x180008444  call    ?CreateWritableConfigSystem@NATIVE_READER@@SAJHPEBG00PEAPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::CreateWritableConfigSystem(int,ushort const *,ushort const *,ushort const *,INativeConfigurationSystem * *)
0x180008449  mov     ebx, eax
0x18000844b  test    eax, eax
0x18000844d  js      loc_18000852E
0x180008453  mov     ecx, 0C0h; Size
0x180008458  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000845d  mov     rdi, [rbp+57h+var_B0]
0x180008461  mov     rsi, rax
0x180008464  test    rax, rax
0x180008467  jz      loc_180008527
0x18000846d  mov     [rsi+8], r13
0x180008471  lea     rax, ??_7CONFIG_SYSTEM_ENTRY@@6B@; const CONFIG_SYSTEM_ENTRY::`vftable'
0x180008478  mov     [rsi], rax
0x18000847b  mov     ecx, 20h ; ' '
0x180008480  lea     rax, [rsi+10h]
0x180008484  mov     rdx, rdi; struct INativeConfigurationSystem *
0x180008487  mov     [rax+28h], ecx
0x18000848a  mov     [rax], r13
0x18000848d  mov     [rax+20h], rax
0x180008491  mov     word ptr [rax+2Ch], 100h
0x180008497  mov     [rax+30h], r13d
0x18000849b  lea     rax, [rsi+48h]
0x18000849f  mov     [rax+28h], ecx
0x1800084a2  mov     [rax], r13
0x1800084a5  mov     [rax+20h], rax
0x1800084a9  mov     word ptr [rax+2Ch], 100h
0x1800084af  mov     [rax+30h], r13d
0x1800084b3  lea     rax, [rsi+80h]
0x1800084ba  mov     [rax+28h], ecx
0x1800084bd  mov     rcx, rsi; this
0x1800084c0  mov     [rax], r13
0x1800084c3  mov     [rax+20h], rax
0x1800084c7  mov     word ptr [rax+2Ch], 100h
0x1800084cd  mov     [rax+30h], r13d
0x1800084d1  mov     [rsi+0B8h], r13
0x1800084d8  mov     rax, [r14+0A0h]
0x1800084df  mov     r9, [rbp+57h+String1]; unsigned __int16 *
0x1800084e3  mov     r8d, [r14+0BCh]; int
0x1800084ea  mov     [rsp+0E0h+var_B8], rax; unsigned __int16 *
0x1800084ef  mov     rax, [r14+68h]
0x1800084f3  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 *
0x1800084f8  call    ?Create@CONFIG_SYSTEM_ENTRY@@QEAAJPEAVINativeConfigurationSystem@@HPEBG11@Z; CONFIG_SYSTEM_ENTRY::Create(INativeConfigurationSystem *,int,ushort const *,ushort const *,ushort const *)
0x1800084fd  mov     ebx, eax
0x1800084ff  test    eax, eax
0x180008501  js      short loc_180008532
0x180008503  lea     rcx, [r14+138h]; this
0x18000850a  mov     r8d, r15d; unsigned int
0x18000850d  mov     rdx, rsi; struct IArrayListEntry *
0x180008510  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180008515  mov     ebx, eax
0x180008517  test    eax, eax
0x180008519  js      short loc_180008532
0x18000851b  mov     [r12], rdi
0x18000851f  mov     rdi, r13
0x180008522  mov     rsi, r13
0x180008525  jmp     short loc_180008532
0x180008527  mov     ebx, 80070008h
0x18000852c  jmp     short loc_180008522
0x18000852e  mov     rdi, [rbp+57h+var_B0]
0x180008532  test    rdi, rdi
0x180008535  jz      short loc_180008546
0x180008537  mov     rax, [rdi]
0x18000853a  mov     rcx, rdi
0x18000853d  mov     rax, [rax+10h]
0x180008541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008546  test    rsi, rsi
0x180008549  jz      short loc_180008559
0x18000854b  mov     rax, [rsi]
0x18000854e  mov     rcx, rsi
0x180008551  mov     rax, [rax]
0x180008554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008559  lea     rcx, [rbp+57h+var_70]; this
0x18000855d  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180008562  lea     rcx, [rbp+57h+var_A8]; this
0x180008566  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000856b  mov     eax, ebx
0x18000856d  mov     rcx, [rbp+57h+var_38]
0x180008571  xor     rcx, rsp; StackCookie
0x180008574  call    __security_check_cookie
0x180008579  mov     rbx, [rsp+0E0h+arg_18]
0x180008581  add     rsp, 0B0h
0x180008588  pop     r15
0x18000858a  pop     r14
0x18000858c  pop     r13
0x18000858e  pop     r12
0x180008590  pop     rdi
0x180008591  pop     rsi
0x180008592  pop     rbp
0x180008593  retn
```
