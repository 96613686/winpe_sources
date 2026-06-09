# OBJECT_EXTENSION::SetObjectType(ushort const *,ushort const *,ulong)

- ea: `0x180012b28`
- end: `0x180012cd8`
- name: `?SetObjectType@OBJECT_EXTENSION@@IEAAJPEBG0K@Z`
- size: `432`
- prototype: `int(OBJECT_EXTENSION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int)`
- caller_count: `11`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180011ea0`
- `0x180014f50`
- `0x180016c30`
- `0x180018400`
- `0x18001b0b0`
- `0x18001eb40`
- `0x18001fa00`
- `0x1800227e0`
- `0x180024e70`
- `0x180028bd0`
- `0x18002c900`

## callees

- `0x180001044`
- `0x180001fb0`
- `0x180002e90`
- `0x180012b28`
- `0x1800131d8`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## pseudocode

```c
__int64 __fastcall OBJECT_EXTENSION::SetObjectType(
        OBJECT_EXTENSION *this,
        const unsigned __int8 *a2,
        const unsigned __int8 *a3,
        DWORD a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  int v10; // edi
  __int64 v11; // rcx
  va_list Arguments; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v14[32]; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+50h] [rbp-B0h]
  __int16 v17; // [rsp+54h] [rbp-ACh]
  int v18; // [rsp+58h] [rbp-A8h]
  __int16 v19; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v20[1022]; // [rsp+62h] [rbp-9Eh] BYREF

  memset_0(v20, 0, sizeof(v20));
  v16 = 1024;
  v17 = 256;
  v15 = (unsigned __int16 *)&v19;
  v18 = 0;
  v19 = 0;
  Arguments = 0;
  v8 = operator new(0xC0u);
  v9 = v8;
  if ( v8 )
  {
    v8[4] = 1;
    *(_QWORD *)v8 = &OBJECT_TYPE::`vftable'{for `ICommandObjectType'};
    *((_QWORD *)v8 + 1) = &OBJECT_TYPE::`vftable'{for `IArrayListEntry'};
    *((_QWORD *)v8 + 3) = 0;
    *((_QWORD *)v8 + 7) = v8 + 6;
    v8[16] = 32;
    *((_WORD *)v8 + 34) = 256;
    v8[18] = 0;
    *((_QWORD *)v8 + 10) = 0;
    *((_QWORD *)v8 + 14) = v8 + 20;
    v8[30] = 32;
    *((_WORD *)v8 + 62) = 256;
    v8[32] = 0;
    *((_QWORD *)v8 + 17) = 0;
    *((_QWORD *)v8 + 21) = v8 + 34;
    v8[44] = 32;
    *((_WORD *)v8 + 90) = 256;
    v8[46] = 0;
  }
  else
  {
    v9 = 0;
  }
  v10 = FormatCommandMessage(a4, &Arguments, (struct STRU *)v14);
  if ( v10 < 0 )
  {
    if ( v9 )
LABEL_13:
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  }
  else
  {
    if ( STRU::Copy((STRU *)(v9 + 6), a2) >= 0 && STRU::Copy((STRU *)(v9 + 20), a3) >= 0 )
      STRU::Copy((STRU *)(v9 + 34), (const unsigned __int8 *)v15);
    if ( v9 )
    {
      v11 = *((_QWORD *)this + 2);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      *((_QWORD *)this + 2) = v9;
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 8LL))(v9);
      goto LABEL_13;
    }
  }
  BUFFER::~BUFFER((BUFFER *)v14);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180012b28  push    rbp
0x180012b2a  push    rbx
0x180012b2b  push    rsi
0x180012b2c  push    rdi
0x180012b2d  push    r12
0x180012b2f  push    r14
0x180012b31  push    r15
0x180012b33  lea     rbp, [rsp-370h]
0x180012b3b  sub     rsp, 470h
0x180012b42  mov     rax, cs:__security_cookie
0x180012b49  xor     rax, rsp
0x180012b4c  mov     [rbp+3A0h+var_40], rax
0x180012b53  mov     r15, r8
0x180012b56  mov     r14, rdx
0x180012b59  mov     rsi, rcx
0x180012b5c  xor     edx, edx; Val
0x180012b5e  mov     r8d, 3FEh; Size
0x180012b64  lea     rcx, [rsp+4A0h+var_43E]; void *
0x180012b69  mov     edi, r9d
0x180012b6c  call    memset_0
0x180012b71  xor     r12d, r12d
0x180012b74  mov     [rsp+4A0h+var_450], 400h
0x180012b7c  lea     rax, [rsp+4A0h+var_440]
0x180012b81  mov     [rsp+4A0h+var_44C], 100h
0x180012b88  mov     ecx, 0C0h; Size
0x180012b8d  mov     [rsp+4A0h+var_458], rax
0x180012b92  mov     [rsp+4A0h+var_448], r12d
0x180012b97  mov     [rsp+4A0h+var_440], r12w
0x180012b9d  mov     [rsp+4A0h+Arguments], r12
0x180012ba2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012ba7  mov     rbx, rax
0x180012baa  test    rax, rax
0x180012bad  jz      short loc_180012C1D
0x180012baf  mov     dword ptr [rbx+10h], 1
0x180012bb6  lea     ecx, [r12+20h]
0x180012bbb  lea     rax, ??_7OBJECT_TYPE@@6BICommandObjectType@@@; const OBJECT_TYPE::`vftable'{for `ICommandObjectType'}
0x180012bc2  mov     [rbx], rax
0x180012bc5  lea     rax, ??_7OBJECT_TYPE@@6BIArrayListEntry@@@; const OBJECT_TYPE::`vftable'{for `IArrayListEntry'}
0x180012bcc  mov     [rbx+8], rax
0x180012bd0  lea     rax, [rbx+18h]
0x180012bd4  mov     [rax], r12
0x180012bd7  mov     [rax+20h], rax
0x180012bdb  mov     [rax+28h], ecx
0x180012bde  mov     word ptr [rax+2Ch], 100h
0x180012be4  mov     [rax+30h], r12d
0x180012be8  lea     rax, [rbx+50h]
0x180012bec  mov     [rax], r12
0x180012bef  mov     [rax+20h], rax
0x180012bf3  mov     [rax+28h], ecx
0x180012bf6  mov     word ptr [rax+2Ch], 100h
0x180012bfc  mov     [rax+30h], r12d
0x180012c00  lea     rax, [rbx+88h]
0x180012c07  mov     [rax], r12
0x180012c0a  mov     [rax+20h], rax
0x180012c0e  mov     [rax+28h], ecx
0x180012c11  mov     word ptr [rax+2Ch], 100h
0x180012c17  mov     [rax+30h], r12d
0x180012c1b  jmp     short loc_180012C20
0x180012c1d  mov     rbx, r12
0x180012c20  lea     r8, [rsp+4A0h+var_478]; this
0x180012c25  mov     ecx, edi; dwMessageId
0x180012c27  lea     rdx, [rsp+4A0h+Arguments]; Arguments
0x180012c2c  call    ?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z; FormatCommandMessage(ulong,ushort const * * const,STRU *)
0x180012c31  mov     edi, eax
0x180012c33  test    eax, eax
0x180012c35  js      short loc_180012C97
0x180012c37  lea     rcx, [rbx+18h]; this
0x180012c3b  mov     rdx, r14; unsigned __int16 *
0x180012c3e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012c43  test    eax, eax
0x180012c45  js      short loc_180012C68
0x180012c47  lea     rcx, [rbx+50h]; this
0x180012c4b  mov     rdx, r15; unsigned __int16 *
0x180012c4e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012c53  test    eax, eax
0x180012c55  js      short loc_180012C68
0x180012c57  mov     rdx, [rsp+4A0h+var_458]; unsigned __int16 *
0x180012c5c  lea     rcx, [rbx+88h]; this
0x180012c63  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180012c68  test    rbx, rbx
0x180012c6b  jz      short loc_180012CAB
0x180012c6d  mov     rcx, [rsi+10h]
0x180012c71  test    rcx, rcx
0x180012c74  jz      short loc_180012C82
0x180012c76  mov     rax, [rcx]
0x180012c79  mov     rax, [rax+10h]
0x180012c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c82  mov     [rsi+10h], rbx
0x180012c86  mov     rcx, rbx
0x180012c89  mov     rax, [rbx]
0x180012c8c  mov     rax, [rax+8]
0x180012c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c95  jmp     short loc_180012C9C
0x180012c97  test    rbx, rbx
0x180012c9a  jz      short loc_180012CAB
0x180012c9c  mov     rax, [rbx]
0x180012c9f  mov     rcx, rbx
0x180012ca2  mov     rax, [rax+10h]
0x180012ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012cab  lea     rcx, [rsp+4A0h+var_478]; this
0x180012cb0  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180012cb5  mov     eax, edi
0x180012cb7  mov     rcx, [rbp+3A0h+var_40]
0x180012cbe  xor     rcx, rsp; StackCookie
0x180012cc1  call    __security_check_cookie
0x180012cc6  add     rsp, 470h
0x180012ccd  pop     r15
0x180012ccf  pop     r14
0x180012cd1  pop     r12
0x180012cd3  pop     rdi
0x180012cd4  pop     rsi
0x180012cd5  pop     rbx
0x180012cd6  pop     rbp
0x180012cd7  retn
```
