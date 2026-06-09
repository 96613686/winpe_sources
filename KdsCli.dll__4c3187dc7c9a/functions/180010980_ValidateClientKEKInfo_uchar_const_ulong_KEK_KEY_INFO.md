# ValidateClientKEKInfo(uchar * const,ulong,_KEK_KEY_INFO * *)

- ea: `0x180010980`
- end: `0x180010a8d`
- name: `?ValidateClientKEKInfo@@YAJQEAEKPEAPEAU_KEK_KEY_INFO@@@Z`
- size: `269`
- prototype: `__int64 __fastcall(unsigned __int8 *const, unsigned int, struct _KEK_KEY_INFO **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009408`
- `0x180017030`
- `0x180019bec`

## callees

- `0x180010980`
- `0x180010cf8`
- `0x18001a450`

## string_xrefs

- `0x1800109d2`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x180010a5e`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall ValidateClientKEKInfo(unsigned __int8 *const a1, unsigned int a2, struct _KEK_KEY_INFO **a3)
{
  unsigned int v6; // r9d
  __int64 v7; // r9
  unsigned int v8; // eax
  unsigned int v9; // r9d
  unsigned int v10; // ebx
  __int64 v11; // r8
  unsigned int v12; // ecx
  __int64 v13; // rdx
  __int64 v14; // r8

  if ( !ValidateSIDKeyID(a1, a2) )
  {
    v6 = 517;
LABEL_21:
    v10 = -2146893821;
    SidKeyDebugTraceError(0x80090003, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v6);
    return v10;
  }
  if ( a2 < 0x34 )
  {
    v6 = 525;
    goto LABEL_21;
  }
  v7 = *((unsigned int *)a1 + 10);
  v8 = v7 + 52;
  if ( (unsigned int)v7 >= 0xFFFFFFCC )
  {
    v9 = 535;
LABEL_7:
    SidKeyDebugTraceError(0x80070216, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v9);
    return (unsigned int)-2146893821;
  }
  v11 = *((unsigned int *)a1 + 11);
  v12 = v8 + v11;
  if ( v8 + (unsigned int)v11 < v8 )
  {
    v9 = 543;
    goto LABEL_7;
  }
  v13 = *((unsigned int *)a1 + 12);
  if ( (unsigned int)v13 + v12 < v12 )
  {
    v9 = 551;
    goto LABEL_7;
  }
  if ( a2 != (_DWORD)v13 + v12 )
  {
    v6 = 560;
    goto LABEL_21;
  }
  if ( (v11 & 1) != 0 || (v14 = v7 + v11, *(_WORD *)&a1[v14 + 50]) )
  {
    v6 = 570;
    goto LABEL_21;
  }
  if ( (v13 & 1) != 0 || *(_WORD *)&a1[v14 + 50 + v13] )
  {
    v6 = 581;
    goto LABEL_21;
  }
  v10 = 0;
  *a3 = (struct _KEK_KEY_INFO *)a1;
  return v10;
}

```

## disassembly

```asm
0x180010980  mov     [rsp+arg_0], rbx
0x180010985  mov     [rsp+arg_8], rsi
0x18001098a  push    rdi
0x18001098b  sub     rsp, 20h
0x18001098f  mov     rsi, r8
0x180010992  mov     ebx, edx
0x180010994  mov     rdi, rcx
0x180010997  call    ?ValidateSIDKeyID@@YAPEAU_SID_KEY_ID_HEADER@@QEAEK@Z; ValidateSIDKeyID(uchar * const,ulong)
0x18001099c  xor     r10d, r10d
0x18001099f  test    rax, rax
0x1800109a2  jnz     short loc_1800109AF
0x1800109a4  mov     r9d, 205h
0x1800109aa  jmp     loc_180010A5E
0x1800109af  cmp     ebx, 34h ; '4'
0x1800109b2  jnb     short loc_1800109BF
0x1800109b4  mov     r9d, 20Dh
0x1800109ba  jmp     loc_180010A5E
0x1800109bf  mov     r9d, [rdi+28h]
0x1800109c3  lea     eax, [r9+34h]
0x1800109c7  cmp     eax, 34h ; '4'
0x1800109ca  jnb     short loc_1800109F4
0x1800109cc  mov     r9d, 217h; unsigned int
0x1800109d2  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x1800109d9  mov     ecx, 80070216h; unsigned int
0x1800109de  lea     rdx, aHr; "hr"
0x1800109e5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x1800109ea  mov     ebx, 80090003h
0x1800109ef  jmp     loc_180010A7B
0x1800109f4  mov     r8d, [rdi+2Ch]
0x1800109f8  lea     ecx, [rax+r8]
0x1800109fc  cmp     ecx, eax
0x1800109fe  jnb     short loc_180010A08
0x180010a00  mov     r9d, 21Fh
0x180010a06  jmp     short loc_1800109D2
0x180010a08  mov     edx, [rdi+30h]
0x180010a0b  lea     eax, [rdx+rcx]
0x180010a0e  cmp     eax, ecx
0x180010a10  jnb     short loc_180010A1A
0x180010a12  mov     r9d, 227h
0x180010a18  jmp     short loc_1800109D2
0x180010a1a  cmp     ebx, eax
0x180010a1c  jz      short loc_180010A26
0x180010a1e  mov     r9d, 230h
0x180010a24  jmp     short loc_180010A5E
0x180010a26  test    r8b, 1
0x180010a2a  jnz     short loc_180010A58
0x180010a2c  add     r8, r9
0x180010a2f  cmp     [r8+rdi+32h], r10w
0x180010a35  jnz     short loc_180010A58
0x180010a37  test    dl, 1
0x180010a3a  jnz     short loc_180010A50
0x180010a3c  lea     rax, [r8+rdx]
0x180010a40  cmp     [rax+rdi+32h], r10w
0x180010a46  jnz     short loc_180010A50
0x180010a48  mov     ebx, r10d
0x180010a4b  mov     [rsi], rdi
0x180010a4e  jmp     short loc_180010A7B
0x180010a50  mov     r9d, 245h
0x180010a56  jmp     short loc_180010A5E
0x180010a58  mov     r9d, 23Ah; unsigned int
0x180010a5e  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x180010a65  mov     ecx, 80090003h; unsigned int
0x180010a6a  lea     rdx, aHr; "hr"
0x180010a71  mov     ebx, 80090003h
0x180010a76  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x180010a7b  mov     rsi, [rsp+28h+arg_8]
0x180010a80  mov     eax, ebx
0x180010a82  mov     rbx, [rsp+28h+arg_0]
0x180010a87  add     rsp, 20h
0x180010a8b  pop     rdi
0x180010a8c  retn
```
