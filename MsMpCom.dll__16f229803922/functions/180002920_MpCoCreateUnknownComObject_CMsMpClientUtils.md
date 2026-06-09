# MpCoCreateUnknownComObject_CMsMpClientUtils_

- ea: `0x180002920`
- end: `0x180002a57`
- name: `MpCoCreateUnknownComObject_CMsMpClientUtils_`
- size: `311`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003b30`

## callees

- `0x180002920`
- `0x1800038bc`
- `0x180005b0c`
- `0x18000a010`

## import_xrefs

- `mpclient!MpManagerOpen` at `0x1800029b4`
- `mpclient!MpManagerOpen` at `0x1800029b4`
- `mpclient!MpHandleClose` at `0x1800029a2`
- `mpclient!MpHandleClose` at `0x1800029a2`

## pseudocode

```c
__int64 __fastcall MpCoCreateUnknownComObject_CMsMpClientUtils_(_QWORD *a1)
{
  int v2; // edi
  __int64 v3; // rbx
  __int64 v4; // rcx
  __int64 (__fastcall ***v5)(__int64, GUID *, __int64 *); // rcx
  __int64 (__fastcall **v6)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall ***v8)(__int64, GUID *, __int64 *); // rbx
  __int64 v9; // rax
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a1 = 0;
  v11 = 0;
  v2 = ATL::CComObject<CMsMpClientUtils>::CreateInstance(&v11);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v3 = v11;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)(v11 + 64) + 8LL))(v11 + 64);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10);
  v4 = *(_QWORD *)(v3 + 72);
  if ( v4 )
  {
    MpHandleClose(v4);
    *(_QWORD *)(v3 + 72) = 0;
  }
  v2 = MpManagerOpen(0, v3 + 72);
  if ( v2 < 0 )
  {
    if ( !v3 )
      return (unsigned int)v2;
    v5 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 *))(v3 + 64);
    v6 = *(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))(v3 + 64);
LABEL_10:
    ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))v6[2])(v5);
    return (unsigned int)v2;
  }
  v10 = 0;
  v8 = (__int64 (__fastcall ***)(__int64, GUID *, __int64 *))(v3 + 64);
  v2 = (**v8)((__int64)v8, &GUID_00000000_0000_0000_c000_000000000046, &v10);
  if ( v2 < 0 )
  {
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    v6 = *v8;
    v5 = v8;
    goto LABEL_10;
  }
  v9 = v10;
  v10 = 0;
  *a1 = v9;
  ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *)))(*v8)[2])(v8);
  return 0;
}

```

## disassembly

```asm
0x180002920  mov     rax, rsp
0x180002923  mov     [rax+18h], rbx
0x180002927  mov     [rax+20h], rsi
0x18000292b  push    rdi
0x18000292c  sub     rsp, 30h
0x180002930  mov     rsi, rcx
0x180002933  mov     qword ptr [rcx], 0
0x18000293a  mov     qword ptr [rax+10h], 0
0x180002942  lea     rcx, [rax+10h]
0x180002946  call    ?CreateInstance@?$CComObject@VCMsMpClientUtils@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMsMpClientUtils>::CreateInstance(ATL::CComObject<CMsMpClientUtils> * *)
0x18000294b  mov     edi, eax
0x18000294d  test    eax, eax
0x18000294f  js      loc_1800029D5
0x180002955  mov     rbx, [rsp+38h+arg_8]
0x18000295a  lea     rcx, [rbx+40h]
0x18000295e  mov     rax, [rcx]
0x180002961  mov     rax, [rax+8]
0x180002965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296a  lea     rax, WPP_GLOBAL_Control
0x180002971  mov     rcx, cs:WPP_GLOBAL_Control
0x180002978  cmp     rcx, rax
0x18000297b  jz      short loc_180002996
0x18000297d  test    byte ptr [rcx+1Ch], 8
0x180002981  jz      short loc_180002996
0x180002983  mov     edx, 0Ah
0x180002988  mov     [rsp+38h+var_18], rbx
0x18000298d  mov     rcx, [rcx+10h]
0x180002991  call    WPP_SF_sq
0x180002996  lea     rdi, [rbx+48h]
0x18000299a  mov     rcx, [rdi]
0x18000299d  test    rcx, rcx
0x1800029a0  jz      short loc_1800029AF
0x1800029a2  call    cs:__imp_MpHandleClose
0x1800029a8  mov     qword ptr [rdi], 0
0x1800029af  mov     rdx, rdi
0x1800029b2  xor     ecx, ecx
0x1800029b4  call    cs:__imp_MpManagerOpen
0x1800029ba  mov     edi, eax
0x1800029bc  test    eax, eax
0x1800029be  jns     short loc_1800029E7
0x1800029c0  test    rbx, rbx
0x1800029c3  jz      short loc_1800029D5
0x1800029c5  lea     rcx, [rbx+40h]
0x1800029c9  mov     rax, [rcx]
0x1800029cc  mov     rax, [rax+10h]
0x1800029d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d5  mov     eax, edi
0x1800029d7  mov     rbx, [rsp+38h+arg_10]
0x1800029dc  mov     rsi, [rsp+38h+arg_18]
0x1800029e1  add     rsp, 30h
0x1800029e5  pop     rdi
0x1800029e6  retn
0x1800029e7  mov     [rsp+38h+arg_0], 0
0x1800029f0  add     rbx, 40h ; '@'
0x1800029f4  mov     rax, [rbx]
0x1800029f7  lea     r8, [rsp+38h+arg_0]
0x1800029fc  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002a03  mov     rcx, rbx
0x180002a06  mov     rax, [rax]
0x180002a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0e  mov     edi, eax
0x180002a10  test    eax, eax
0x180002a12  jns     short loc_180002A33
0x180002a14  mov     rcx, [rsp+38h+arg_0]
0x180002a19  test    rcx, rcx
0x180002a1c  jz      short loc_180002A2B
0x180002a1e  mov     rdx, [rcx]
0x180002a21  mov     rax, [rdx+10h]
0x180002a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2a  nop
0x180002a2b  mov     rax, [rbx]
0x180002a2e  mov     rcx, rbx
0x180002a31  jmp     short loc_1800029CC
0x180002a33  mov     rax, [rsp+38h+arg_0]
0x180002a38  mov     [rsp+38h+arg_0], 0
0x180002a41  mov     [rsi], rax
0x180002a44  mov     rax, [rbx]
0x180002a47  mov     rcx, rbx
0x180002a4a  mov     rax, [rax+10h]
0x180002a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a53  xor     eax, eax
0x180002a55  jmp     short loc_1800029D7
```
