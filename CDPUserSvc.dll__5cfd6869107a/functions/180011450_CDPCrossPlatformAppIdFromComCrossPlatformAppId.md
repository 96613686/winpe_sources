# CDPCrossPlatformAppIdFromComCrossPlatformAppId

- ea: `0x180011450`
- end: `0x180011664`
- name: `CDPCrossPlatformAppIdFromComCrossPlatformAppId`
- size: `532`
- prototype: ``
- caller_count: `14`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007d10`
- `0x180021b90`
- `0x180021df0`
- `0x180022200`
- `0x180022370`
- `0x1800224c0`
- `0x1800226e0`
- `0x1800229c0`
- `0x180022cf0`
- `0x180022f10`
- `0x1800234f0`
- `0x180023970`
- `0x180024060`
- `0x180024310`

## callees

- `0x1800097d0`
- `0x180011450`
- `0x18001e798`
- `0x18002c5a0`
- `0x180064010`

## import_xrefs

- `cdp!CDPCreateCrossPlatformAppId` at `0x18001148f`
- `cdp!CDPCreateCrossPlatformAppId` at `0x18001148f`

## string_xrefs

- `0x1800115ca`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`
- `0x1800115f2`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDPCrossPlatformAppIdFromComCrossPlatformAppId(unsigned int *a1, _QWORD *a2)
{
  int v4; // ebp
  std::_Ref_count_base *v5; // rbx
  std::_Ref_count_base **v6; // rax
  volatile signed __int32 *v7; // rbx
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rax
  volatile signed __int32 *v11; // rbx
  __int64 v13; // rdx
  std::_Ref_count_base **v14; // rdx
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16[2]; // [rsp+20h] [rbp-58h] BYREF
  std::_Ref_count_base *v17; // [rsp+30h] [rbp-48h] BYREF
  std::_Ref_count_base **v18; // [rsp+38h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  _DWORD *v20; // [rsp+88h] [rbp+10h]

  if ( a2 )
  {
    *a2 = 0;
    *(_OWORD *)v16 = 0;
    v17 = 0;
    v18 = v16;
    v4 = CDPCreateCrossPlatformAppId(&v17);
    v5 = v17;
    if ( v17 )
    {
      v20 = operator new(0x18u);
      *(_OWORD *)v20 = 0;
      v20[2] = 1;
      v20[3] = 1;
      *(_QWORD *)v20 = &std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable';
      *((_QWORD *)v20 + 2) = v5;
      v6 = v18;
      *v18 = v5;
      v7 = (volatile signed __int32 *)v6[1];
      v6[1] = (std::_Ref_count_base *)v20;
      if ( v7 )
      {
        if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
    }
    else
    {
      v14 = v18;
      *v18 = 0;
      v15 = v14[1];
      v14[1] = 0;
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
    }
    if ( v4 < 0 )
    {
      v13 = 71;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
        (const char *)(unsigned int)v4,
        (int)v16[0]);
      if ( v16[1] )
        std::_Ref_count_base::_Decref(v16[1]);
      return (unsigned int)v4;
    }
    else
    {
      v8 = (_QWORD *)*((_QWORD *)a1 + 1);
      v9 = &v8[2 * *a1];
      while ( 1 )
      {
        v10 = *(_QWORD *)v16[0];
        if ( v8 == v9 )
          break;
        v4 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD))(v10 + 64))(v16[0], *v8, v8[1]);
        if ( v4 < 0 )
        {
          v13 = 74;
          goto LABEL_19;
        }
        v8 += 2;
      }
      (*(void (**)(void))(v10 + 8))();
      *a2 = v16[0];
      v11 = (volatile signed __int32 *)v16[1];
      if ( v16[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v16[1] + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      return 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x43,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)0x80004003LL,
      (int)v16[0]);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180011450  push    rbx
0x180011452  push    rbp
0x180011453  push    rsi
0x180011454  push    rdi
0x180011455  push    r14
0x180011457  push    r15
0x180011459  sub     rsp, 48h
0x18001145d  mov     r14, rdx
0x180011460  mov     rdi, rcx
0x180011463  test    rdx, rdx
0x180011466  jz      loc_1800115BF
0x18001146c  xor     r15d, r15d
0x18001146f  mov     [rdx], r15
0x180011472  xorps   xmm0, xmm0
0x180011475  movdqu  xmmword ptr [rsp+78h+var_58], xmm0; int
0x18001147b  mov     [rsp+78h+var_48], r15
0x180011480  lea     rax, [rsp+78h+var_58]
0x180011485  mov     [rsp+78h+var_40], rax
0x18001148a  lea     rcx, [rsp+78h+var_48]
0x18001148f  call    cs:__imp_CDPCreateCrossPlatformAppId
0x180011495  mov     ebp, eax
0x180011497  mov     esi, 0FFFFFFFFh
0x18001149c  mov     rbx, [rsp+78h+var_48]
0x1800114a1  test    rbx, rbx
0x1800114a4  jz      loc_180011625
0x1800114aa  mov     ecx, 18h; Size
0x1800114af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800114b4  mov     rcx, rax
0x1800114b7  mov     [rsp+78h+arg_8], rax
0x1800114bf  xorps   xmm0, xmm0
0x1800114c2  movups  xmmword ptr [rax], xmm0
0x1800114c5  mov     dword ptr [rax+8], 1
0x1800114cc  mov     dword ptr [rax+0Ch], 1
0x1800114d3  lea     rax, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppId@@U?$iunknown_deleter@VICDPCrossPlatformAppId@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable'
0x1800114da  mov     [rcx], rax
0x1800114dd  mov     [rcx+10h], rbx
0x1800114e1  mov     rax, [rsp+78h+var_40]
0x1800114e6  mov     [rax], rbx
0x1800114e9  mov     rbx, [rax+8]
0x1800114ed  mov     [rax+8], rcx
0x1800114f1  test    rbx, rbx
0x1800114f4  jz      short loc_180011520
0x1800114f6  mov     eax, esi
0x1800114f8  lock xadd [rbx+8], eax
0x1800114fd  cmp     eax, 1
0x180011500  jnz     short loc_180011520
0x180011502  mov     rax, [rbx]
0x180011505  mov     rcx, rbx
0x180011508  mov     rax, [rax]
0x18001150b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011510  mov     eax, esi
0x180011512  lock xadd [rbx+0Ch], eax
0x180011517  cmp     eax, 1
0x18001151a  jz      loc_180011648
0x180011520  test    ebp, ebp
0x180011522  js      loc_18001165C
0x180011528  mov     rbx, [rdi+8]
0x18001152c  mov     edi, [rdi]
0x18001152e  shl     rdi, 4
0x180011532  add     rdi, rbx
0x180011535  mov     rcx, [rsp+78h+var_58]
0x18001153a  mov     rax, [rcx]
0x18001153d  cmp     rbx, rdi
0x180011540  jz      short loc_180011562
0x180011542  mov     r8, [rbx+8]
0x180011546  mov     rdx, [rbx]
0x180011549  mov     rax, [rax+40h]
0x18001154d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011552  mov     ebp, eax
0x180011554  test    eax, eax
0x180011556  js      loc_1800115ED
0x18001155c  add     rbx, 10h
0x180011560  jmp     short loc_180011535
0x180011562  mov     rax, [rax+8]
0x180011566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001156b  mov     rax, [rsp+78h+var_58]
0x180011570  mov     [r14], rax
0x180011573  mov     rbx, [rsp+78h+var_58+8]
0x180011578  test    rbx, rbx
0x18001157b  jz      short loc_1800115B0
0x18001157d  mov     eax, esi
0x18001157f  lock xadd [rbx+8], eax
0x180011584  cmp     eax, 1
0x180011587  jnz     short loc_1800115B0
0x180011589  mov     rax, [rbx]
0x18001158c  mov     rcx, rbx
0x18001158f  mov     rax, [rax]
0x180011592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011597  lock xadd [rbx+0Ch], esi
0x18001159c  cmp     esi, 1
0x18001159f  jnz     short loc_1800115B0
0x1800115a1  mov     rax, [rbx]
0x1800115a4  mov     rcx, rbx
0x1800115a7  mov     rax, [rax+8]
0x1800115ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115b0  xor     eax, eax
0x1800115b2  add     rsp, 48h
0x1800115b6  pop     r15
0x1800115b8  pop     r14
0x1800115ba  pop     rdi
0x1800115bb  pop     rsi
0x1800115bc  pop     rbp
0x1800115bd  pop     rbx
0x1800115be  retn
0x1800115bf  mov     rcx, [rsp+78h]; this
0x1800115c4  mov     r9d, 80004003h; char *
0x1800115ca  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800115d1  mov     edx, 43h ; 'C'; void *
0x1800115d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800115db  mov     eax, 80004003h
0x1800115e0  add     rsp, 48h
0x1800115e4  pop     r15
0x1800115e6  pop     r14
0x1800115e8  pop     rdi
0x1800115e9  pop     rsi
0x1800115ea  pop     rbp
0x1800115eb  pop     rbx
0x1800115ec  retn
0x1800115ed  mov     edx, 4Ah ; 'J'; void *
0x1800115f2  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x1800115f9  mov     r9d, ebp; char *
0x1800115fc  mov     rcx, [rsp+78h]; this
0x180011601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011606  nop
0x180011607  mov     rcx, [rsp+78h+var_58+8]; this
0x18001160c  test    rcx, rcx
0x18001160f  jz      short loc_180011616
0x180011611  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011616  mov     eax, ebp
0x180011618  add     rsp, 48h
0x18001161c  pop     r15
0x18001161e  pop     r14
0x180011620  pop     rdi
0x180011621  pop     rsi
0x180011622  pop     rbp
0x180011623  pop     rbx
0x180011624  retn
0x180011625  mov     rdx, [rsp+78h+var_40]
0x18001162a  mov     [rdx], r15
0x18001162d  mov     rcx, [rdx+8]; this
0x180011631  mov     [rdx+8], r15
0x180011635  test    rcx, rcx
0x180011638  jz      loc_180011520
0x18001163e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180011643  jmp     loc_180011520
0x180011648  mov     rax, [rbx]
0x18001164b  mov     rcx, rbx
0x18001164e  mov     rax, [rax+8]
0x180011652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011657  jmp     loc_180011520
0x18001165c  mov     edx, 47h ; 'G'
0x180011661  jmp     short loc_1800115F2
```
