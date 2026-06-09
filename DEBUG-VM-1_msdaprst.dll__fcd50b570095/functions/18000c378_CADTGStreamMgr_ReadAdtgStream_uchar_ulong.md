# CADTGStreamMgr::ReadAdtgStream(uchar *,ulong)

- ea: `0x18000c378`
- end: `0x18000c456`
- name: `?ReadAdtgStream@CADTGStreamMgr@@QEAAXPEAEK@Z`
- size: `222`
- prototype: `void __fastcall(CADTGStreamMgr *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c45c`
- `0x18000c498`
- `0x18000c9e8`
- `0x18000cea0`
- `0x18000d014`
- `0x18000ec24`
- `0x18000f04c`
- `0x18000f758`
- `0x1800102a4`
- `0x1800103a0`
- `0x180010c1c`

## callees

- `0x18000c378`
- `0x180015fb4`
- `0x18001a6c8`
- `0x18002cd54`
- `0x180030010`

## pseudocode

```c
void __fastcall CADTGStreamMgr::ReadAdtgStream(CADTGStreamMgr *this, unsigned __int8 *a2, __int64 a3)
{
  __int64 v3; // rcx
  int v4; // ebx
  int v5; // eax
  int v6; // edi
  int v7; // eax
  int v8; // ebx
  int v9; // [rsp+50h] [rbp+18h] BYREF

  if ( (_DWORD)a3 )
  {
    v3 = *(_QWORD *)this;
    v9 = 0;
    v4 = a3;
    v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, __int64, int *))(*(_QWORD *)v3 + 24LL))(v3, a2, a3, &v9);
    v6 = v5;
    if ( v5 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_1800485D8[0] )
          bidTraceW(off_1800481C8[0], 2667520, off_1800485D8[0], (unsigned int)v5, 2605);
      }
      ThrowHR(v6);
    }
    if ( v9 != v4 )
    {
      v7 = Exit(-2147467259, 0x85u);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800485D0[0] )
          bidTraceW(off_1800481C8[0], 2673664, off_1800485D0[0], (unsigned int)v7, 2611);
        ThrowHR(v8);
      }
    }
  }
}

```

## disassembly

```asm
0x18000c378  test    r8d, r8d
0x18000c37b  jz      locret_18000C455
0x18000c381  mov     [rsp+arg_0], rbx
0x18000c386  push    rdi
0x18000c387  sub     rsp, 30h
0x18000c38b  mov     rcx, [rcx]
0x18000c38e  lea     r9, [rsp+38h+arg_10]
0x18000c393  mov     [rsp+38h+arg_10], 0
0x18000c39b  mov     ebx, r8d
0x18000c39e  mov     rax, [rcx]
0x18000c3a1  mov     rax, [rax+18h]
0x18000c3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3aa  mov     edi, eax
0x18000c3ac  test    eax, eax
0x18000c3ae  jns     short loc_18000C3F0
0x18000c3b0  test    byte ptr cs:_bidGblFlags, 2
0x18000c3b7  jz      short loc_18000C3E8
0x18000c3b9  mov     rcx, cs:off_1800485D8; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c3c0  test    rcx, rcx
0x18000c3c3  jz      short loc_18000C3E8
0x18000c3c5  mov     r8, cs:off_1800485D8; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c3cc  mov     r9d, eax
0x18000c3cf  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000c3d6  mov     edx, 28B400h
0x18000c3db  mov     [rsp+38h+var_18], 0A2Dh
0x18000c3e3  call    _bidTraceW
0x18000c3e8  mov     ecx, edi; int
0x18000c3ea  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000c3f0  cmp     [rsp+38h+arg_10], ebx
0x18000c3f4  jz      short loc_18000C44B
0x18000c3f6  mov     edx, 85h; unsigned int
0x18000c3fb  mov     ecx, 80004005h; int
0x18000c400  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18000c405  mov     ebx, eax
0x18000c407  test    eax, eax
0x18000c409  jns     short loc_18000C44B
0x18000c40b  test    byte ptr cs:_bidGblFlags, 2
0x18000c412  jz      short loc_18000C443
0x18000c414  mov     rcx, cs:off_1800485D0; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c41b  test    rcx, rcx
0x18000c41e  jz      short loc_18000C443
0x18000c420  mov     r8, cs:off_1800485D0; "<CADTGStreamMgr::ReadAdtgStream|ADO|ERR"...
0x18000c427  mov     r9d, eax
0x18000c42a  mov     rcx, cs:off_1800481C8; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18000c431  mov     edx, 28CC00h
0x18000c436  mov     [rsp+38h+var_18], 0A33h
0x18000c43e  call    _bidTraceW
0x18000c443  mov     ecx, ebx; int
0x18000c445  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18000c44b  mov     rbx, [rsp+38h+arg_0]
0x18000c450  add     rsp, 30h
0x18000c454  pop     rdi
0x18000c455  retn
```
