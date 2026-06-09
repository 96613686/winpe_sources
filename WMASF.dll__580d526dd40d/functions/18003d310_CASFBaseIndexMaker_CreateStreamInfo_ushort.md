# CASFBaseIndexMaker::CreateStreamInfo(ushort)

- ea: `0x18003d310`
- end: `0x18003d496`
- name: `?CreateStreamInfo@CASFBaseIndexMaker@@MEAAJG@Z`
- size: `390`
- prototype: `__int64 __fastcall(CASFBaseIndexMaker *__hidden this, unsigned __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800015d0`
- `0x180031d98`
- `0x180031e50`
- `0x180032000`
- `0x18003d310`
- `0x180040010`

## pseudocode

```c
__int64 __fastcall CASFBaseIndexMaker::CreateStreamInfo(CASFBaseIndexMaker *this, unsigned __int16 a2)
{
  _QWORD *v4; // rax
  int v5; // ebx
  unsigned __int16 i; // di
  __int64 v7; // rax
  _BYTE v9[600]; // [rsp+30h] [rbp-D0h] BYREF
  _WORD v10[2]; // [rsp+288h] [rbp+188h] BYREF
  __int16 v11; // [rsp+28Ch] [rbp+18Ch] BYREF
  char v12[2]; // [rsp+290h] [rbp+190h] BYREF
  __int16 v13; // [rsp+292h] [rbp+192h]
  __int16 v14; // [rsp+294h] [rbp+194h]
  __int64 v15; // [rsp+298h] [rbp+198h]
  __int64 v16; // [rsp+2A8h] [rbp+1A8h]
  __int64 v17; // [rsp+2B0h] [rbp+1B0h]
  _QWORD v18[5]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int16 v19; // [rsp+2E0h] [rbp+1E0h]
  char v20; // [rsp+2E2h] [rbp+1E2h]
  __int64 v21; // [rsp+4C8h] [rbp+3C8h]
  _QWORD *v22; // [rsp+4D0h] [rbp+3D0h]
  int v23; // [rsp+4D8h] [rbp+3D8h]
  int v24; // [rsp+4E0h] [rbp+3E0h]

  v23 = 0;
  v10[0] = 0;
  v11 = 0;
  v18[1] = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = v18;
  v18[0] = &CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::`vftable';
  v4 = *(_QWORD **)this;
  v24 = 0;
  v5 = ((__int64 (__fastcall *)(CASFBaseIndexMaker *))v4[10])(this);
  if ( v5 >= 0 )
  {
    for ( i = 0; i < a2; ++i )
    {
      v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, __int16 *))(**((_QWORD **)this + 11) + 128LL))(
             *((_QWORD *)this + 11),
             i,
             v10,
             &v11);
      if ( v5 < 0 )
        break;
      v13 = v10[0];
      v14 = v11;
      v12[0] = -1;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v7 = CASFBaseIndexMaker::STREAM_INFO::STREAM_INFO(
             (CASFBaseIndexMaker::STREAM_INFO *)v9,
             (const struct CASFBaseIndexMaker::STREAM_INFO *)v12);
      if ( !(unsigned int)CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::Add((char *)this + 352, v7) )
      {
        v5 = -2147024882;
        break;
      }
    }
  }
  CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>::~CTSparseBlock<unsigned long,CASFBaseIndexMaker::SEEK_POINT,20,0>(v18);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003d310  mov     [rsp-8+arg_8], rbx
0x18003d315  mov     [rsp-8+arg_10], rsi
0x18003d31a  push    rbp
0x18003d31b  push    rdi
0x18003d31c  push    r14
0x18003d31e  lea     rbp, [rsp-400h]
0x18003d326  sub     rsp, 500h
0x18003d32d  mov     rax, cs:__security_cookie
0x18003d334  xor     rax, rsp
0x18003d337  mov     [rbp+410h+var_20], rax
0x18003d33e  xor     eax, eax
0x18003d340  mov     [rbp+410h+var_38], 0
0x18003d34a  mov     [rbp+410h+var_288], ax
0x18003d351  movzx   r14d, dx
0x18003d355  mov     [rbp+410h+var_284], ax
0x18003d35c  mov     rsi, rcx
0x18003d35f  mov     [rbp+410h+var_250], rax
0x18003d366  mov     [rbp+410h+var_230], ax
0x18003d36d  mov     [rbp+410h+var_22E], al
0x18003d373  mov     [rbp+410h+var_48], rax
0x18003d37a  lea     rax, [rbp+410h+var_258]
0x18003d381  mov     [rbp+410h+var_40], rax
0x18003d388  lea     rax, ??_7?$CTDynArray@USEEK_POINT@CASFBaseIndexMaker@@$0BE@@@6B@; const CTDynArray<CASFBaseIndexMaker::SEEK_POINT,20>::`vftable'
0x18003d38f  mov     [rbp+410h+var_258], rax
0x18003d396  mov     rax, [rcx]
0x18003d399  mov     [rbp+410h+var_30], 0
0x18003d3a3  mov     rax, [rax+50h]
0x18003d3a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3ac  mov     ebx, eax
0x18003d3ae  test    eax, eax
0x18003d3b0  js      loc_18003D461
0x18003d3b6  xor     edi, edi
0x18003d3b8  cmp     di, r14w
0x18003d3bc  jnb     loc_18003D461
0x18003d3c2  mov     rcx, [rsi+58h]
0x18003d3c6  lea     r9, [rbp+410h+var_284]
0x18003d3cd  lea     r8, [rbp+410h+var_288]
0x18003d3d4  movzx   edx, di
0x18003d3d7  mov     rax, [rcx]
0x18003d3da  mov     rax, [rax+80h]
0x18003d3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3e6  mov     ebx, eax
0x18003d3e8  test    eax, eax
0x18003d3ea  js      short loc_18003D461
0x18003d3ec  movzx   eax, [rbp+410h+var_288]
0x18003d3f3  lea     rdx, [rbp+410h+var_280]; struct CASFBaseIndexMaker::STREAM_INFO *
0x18003d3fa  mov     [rbp+410h+var_27E], ax
0x18003d401  lea     rcx, [rsp+510h+var_4E0]; this
0x18003d406  movzx   eax, [rbp+410h+var_284]
0x18003d40d  mov     [rbp+410h+var_27C], ax
0x18003d414  mov     [rbp+410h+var_280], 0FFh
0x18003d41b  mov     [rbp+410h+var_278], 0
0x18003d426  mov     [rbp+410h+var_268], 0
0x18003d431  mov     [rbp+410h+var_260], 0
0x18003d43c  call    ??0STREAM_INFO@CASFBaseIndexMaker@@QEAA@AEBU01@@Z; CASFBaseIndexMaker::STREAM_INFO::STREAM_INFO(CASFBaseIndexMaker::STREAM_INFO const &)
0x18003d441  mov     rdx, rax
0x18003d444  lea     rcx, [rsi+160h]
0x18003d44b  call    ?Add@?$CTDynArray@USTREAM_INFO@CASFBaseIndexMaker@@$0BE@@@QEAAHUSTREAM_INFO@CASFBaseIndexMaker@@PEAK@Z; CTDynArray<CASFBaseIndexMaker::STREAM_INFO,20>::Add(CASFBaseIndexMaker::STREAM_INFO,ulong *)
0x18003d450  test    eax, eax
0x18003d452  jz      short loc_18003D45C
0x18003d454  inc     di
0x18003d457  jmp     loc_18003D3B8
0x18003d45c  mov     ebx, 8007000Eh
0x18003d461  lea     rcx, [rbp+410h+var_258]
0x18003d468  call    ??1?$CTSparseBlock@KUSEEK_POINT@CASFBaseIndexMaker@@$0BE@$0A@@@QEAA@XZ; CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>::~CTSparseBlock<ulong,CASFBaseIndexMaker::SEEK_POINT,20,0>(void)
0x18003d46d  mov     eax, ebx
0x18003d46f  mov     rcx, [rbp+410h+var_20]
0x18003d476  xor     rcx, rsp; StackCookie
0x18003d479  call    __security_check_cookie
0x18003d47e  lea     r11, [rsp+510h+var_10]
0x18003d486  mov     rbx, [r11+28h]
0x18003d48a  mov     rsi, [r11+30h]
0x18003d48e  mov     rsp, r11
0x18003d491  pop     r14
0x18003d493  pop     rdi
0x18003d494  pop     rbp
0x18003d495  retn
```
