# CAppInfo::EnforceAssignmentSecurity(int *)

- ea: `0x180005f2c`
- end: `0x1800060f6`
- name: `?EnforceAssignmentSecurity@CAppInfo@@AEAAKPEAH@Z`
- size: `458`
- prototype: `__int64 __fastcall(CAppInfo *this, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005294`

## callees

- `0x1800016d0`
- `0x180005f2c`
- `0x1800093ac`
- `0x1800116e4`
- `0x18001b1a0`
- `0x18001b4e0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall CAppInfo::EnforceAssignmentSecurity(CAppInfo *this, int *a2)
{
  bool v3; // zf
  __int64 v5; // rcx
  unsigned int v6; // edi
  int v8; // edx
  int v9; // eax
  int v10; // [rsp+30h] [rbp-38h] BYREF
  int v11; // [rsp+34h] [rbp-34h] BYREF
  _WORD v12[8]; // [rsp+38h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = *((_DWORD *)this + 59) == 0;
  v10 = 0;
  if ( v3 )
    return 0;
  if ( *(_DWORD *)&gDebugLevel )
    _DebugMsg(4u, 0xC1Bu, *((_QWORD *)this + 5), *((_QWORD *)this + 9));
  if ( (unsigned int)((__int64 (__fastcall *)(_QWORD))gpfnMsiQueryProductState)(*((_QWORD *)this + 10)) - 3 > 2 )
    return 0;
  v5 = *((_QWORD *)this + 10);
  v10 = 8;
  v6 = ((__int64 (__fastcall *)(__int64, const unsigned __int16 *, _WORD *, int *))gpfnMsiGetProductInfo)(
         v5,
         L"AssignmentType",
         v12,
         &v10);
  if ( v6 )
    goto LABEL_6;
  v8 = *(_DWORD *)(*((_QWORD *)this + 2) + 296LL);
  if ( !v8 )
  {
    if ( v12[0] != 49 )
      return 0;
LABEL_13:
    if ( (*((_DWORD *)this + 56) & 0x100) != 0 )
    {
      v11 = 0;
      if ( v8 )
      {
        v6 = ((__int64 (__fastcall *)(_QWORD, int *))gpfnMsiIsProductElevated)(*((_QWORD *)this + 10), &v11);
        if ( v6 )
          goto LABEL_6;
        v9 = v11;
      }
      else
      {
        v9 = 1;
      }
      if ( v9 )
        return 0;
    }
    CEventsBase::Report(
      (CEventsBase *)(*((_QWORD *)this + 2) + 344LL),
      0xCBu,
      0,
      2u,
      *((_QWORD *)this + 5),
      *((_QWORD *)this + 9));
    CManagedAppProcessor::LogonMsg(*((CManagedAppProcessor **)this + 2), 0x3EAu, *((_QWORD *)this + 5));
    v6 = CAppInfo::Uninstall(this, 1);
    CManagedAppProcessor::LogonMsg(*((CManagedAppProcessor **)this + 2), 0x3E8u);
    if ( !v6 )
    {
      *((_DWORD *)this + 54) = 2;
      *a2 = 1;
      return v6;
    }
LABEL_6:
    if ( *(_DWORD *)&gDebugLevel )
      _DebugMsg(2u, 0xC07u, *((_QWORD *)this + 5), v6);
    return v6;
  }
  if ( v12[0] != 49 )
    goto LABEL_13;
  return 0;
}

```

## disassembly

```asm
0x180005f2c  mov     [rsp+arg_10], rbx
0x180005f31  push    rsi
0x180005f32  push    rdi
0x180005f33  push    r14
0x180005f35  sub     rsp, 50h
0x180005f39  mov     rax, cs:__security_cookie
0x180005f40  xor     rax, rsp
0x180005f43  mov     [rsp+68h+var_20], rax
0x180005f48  mov     dword ptr [rdx], 0
0x180005f4e  mov     rsi, rdx
0x180005f51  cmp     dword ptr [rcx+0ECh], 0
0x180005f58  mov     rbx, rcx
0x180005f5b  mov     [rsp+68h+var_38], 0
0x180005f63  jz      loc_180006016
0x180005f69  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180005f70  jz      short loc_180005F89
0x180005f72  mov     r9, [rcx+48h]
0x180005f76  mov     edx, 0C1Bh; unsigned int
0x180005f7b  mov     r8, [rcx+28h]
0x180005f7f  mov     ecx, 4; unsigned int
0x180005f84  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005f89  mov     rcx, [rbx+50h]
0x180005f8d  mov     rax, cs:?gpfnMsiQueryProductState@@3P6A?AW4tagINSTALLSTATE@@PEBG@ZEA; tagINSTALLSTATE (*gpfnMsiQueryProductState)(ushort const *)
0x180005f94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f99  add     eax, 0FFFFFFFDh
0x180005f9c  mov     r14d, 2
0x180005fa2  cmp     eax, r14d
0x180005fa5  ja      short loc_180006016
0x180005fa7  mov     rcx, [rbx+50h]
0x180005fab  lea     r9, [rsp+68h+var_38]
0x180005fb0  mov     rax, cs:?gpfnMsiGetProductInfo@@3P6AIPEBG0PEAGPEAK@ZEA; uint (*gpfnMsiGetProductInfo)(ushort const *,ushort const *,ushort *,ulong *)
0x180005fb7  lea     r8, [rsp+68h+var_30]
0x180005fbc  lea     rdx, aAssignmenttype; "AssignmentType"
0x180005fc3  mov     [rsp+68h+var_38], 8
0x180005fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd0  mov     edi, eax
0x180005fd2  test    eax, eax
0x180005fd4  jz      short loc_180005FF7
0x180005fd6  cmp     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180005fdd  jz      short loc_180005FF3
0x180005fdf  mov     r8, [rbx+28h]
0x180005fe3  mov     r9d, edi
0x180005fe6  mov     edx, 0C07h; unsigned int
0x180005feb  mov     ecx, r14d; unsigned int
0x180005fee  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x180005ff3  mov     eax, edi
0x180005ff5  jmp     short loc_180006018
0x180005ff7  xor     ecx, ecx
0x180005ff9  lea     eax, [rcx+31h]
0x180005ffc  cmp     ax, [rsp+68h+var_30]
0x180006001  mov     rax, [rbx+10h]
0x180006005  setz    cl
0x180006008  mov     edx, [rax+128h]
0x18000600e  test    edx, edx
0x180006010  jz      short loc_180006036
0x180006012  test    ecx, ecx
0x180006014  jz      short loc_18000603A
0x180006016  xor     eax, eax
0x180006018  mov     rcx, [rsp+68h+var_20]
0x18000601d  xor     rcx, rsp; StackCookie
0x180006020  call    __security_check_cookie
0x180006025  mov     rbx, [rsp+68h+arg_10]
0x18000602d  add     rsp, 50h
0x180006031  pop     r14
0x180006033  pop     rdi
0x180006034  pop     rsi
0x180006035  retn
0x180006036  test    ecx, ecx
0x180006038  jz      short loc_180006016
0x18000603a  test    dword ptr [rbx+0E0h], 100h
0x180006044  jz      short loc_180006080
0x180006046  mov     [rsp+68h+var_34], 0
0x18000604e  test    edx, edx
0x180006050  jz      short loc_180006077
0x180006052  mov     rcx, [rbx+50h]
0x180006056  lea     rdx, [rsp+68h+var_34]
0x18000605b  mov     rax, cs:?gpfnMsiIsProductElevated@@3P6AIPEBGPEAH@ZEA; uint (*gpfnMsiIsProductElevated)(ushort const *,int *)
0x180006062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006067  mov     edi, eax
0x180006069  test    eax, eax
0x18000606b  jnz     loc_180005FD6
0x180006071  mov     eax, [rsp+68h+var_34]
0x180006075  jmp     short loc_18000607C
0x180006077  mov     eax, 1
0x18000607c  test    eax, eax
0x18000607e  jnz     short loc_180006016
0x180006080  mov     rax, [rbx+48h]
0x180006084  mov     r9d, r14d; unsigned __int16
0x180006087  mov     rcx, [rbx+10h]
0x18000608b  xor     r8d, r8d; int
0x18000608e  mov     [rsp+68h+var_40], rax
0x180006093  add     rcx, 158h; this
0x18000609a  mov     rax, [rbx+28h]
0x18000609e  mov     edx, 0CBh; unsigned int
0x1800060a3  mov     [rsp+68h+var_48], rax
0x1800060a8  call    ?Report@CEventsBase@@QEAAXKHGZZ; CEventsBase::Report(ulong,int,ushort,...)
0x1800060ad  mov     r8, [rbx+28h]
0x1800060b1  mov     edx, 3EAh; unsigned int
0x1800060b6  mov     rcx, [rbx+10h]; this
0x1800060ba  call    ?LogonMsg@CManagedAppProcessor@@AEAAXKZZ; CManagedAppProcessor::LogonMsg(ulong,...)
0x1800060bf  mov     edx, 1; int
0x1800060c4  mov     rcx, rbx; this
0x1800060c7  call    ?Uninstall@CAppInfo@@QEAAKH@Z; CAppInfo::Uninstall(int)
0x1800060cc  mov     rcx, [rbx+10h]; this
0x1800060d0  mov     edx, 3E8h; unsigned int
0x1800060d5  mov     edi, eax
0x1800060d7  call    ?LogonMsg@CManagedAppProcessor@@AEAAXKZZ; CManagedAppProcessor::LogonMsg(ulong,...)
0x1800060dc  test    edi, edi
0x1800060de  jnz     loc_180005FD6
0x1800060e4  mov     [rbx+0D8h], r14d
0x1800060eb  mov     dword ptr [rsi], 1
0x1800060f1  jmp     loc_180005FF3
```
