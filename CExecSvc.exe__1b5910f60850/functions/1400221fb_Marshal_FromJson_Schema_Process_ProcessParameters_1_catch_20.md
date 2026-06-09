# _Marshal::FromJson_Schema::Process::ProcessParameters__::_1_::catch$20

- ea: `0x1400221fb`
- end: `0x14002239e`
- name: `_Marshal::FromJson_Schema::Process::ProcessParameters__::_1_::catch$20`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140002378`
- `0x1400068ac`
- `0x140007a24`
- `0x14000ddf4`
- `0x14000e884`
- `0x1400221fb`

## pseudocode

```c
__int64 __fastcall Marshal::FromJson_Schema::Process::ProcessParameters__::_1_::catch_20(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  __int64 v4; // rdi
  __int64 v5; // rax
  __int64 *v6; // rdi
  unsigned __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 v10; // r14

  *(_OWORD *)(a2 + 144) = 0;
  *(_QWORD *)(a2 + 160) = 0;
  *(_QWORD *)(a2 + 168) = 0;
  std::wstring::_Construct<1,unsigned short const *>(a2 + 144, L"$", 1u);
  *(_DWORD *)(a2 + 176) = 13;
  *(_OWORD *)(a2 + 80) = 0;
  *(_QWORD *)(a2 + 96) = 0;
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(a2 + 80, 1);
  *(_QWORD *)(a2 + 128) = a2 + 80;
  v3 = *(_QWORD *)(a2 + 80);
  v4 = a2 + 144;
  *(_OWORD *)(a2 + 56) = 0;
  *(_QWORD *)(a2 + 56) = v3;
  *(_QWORD *)(a2 + 64) = v3;
  *(_QWORD *)(a2 + 72) = a2 + 80;
  do
  {
    std::wstring::wstring(v3, v4);
    *(_DWORD *)(v3 + 32) = *(_DWORD *)(v4 + 32);
    v3 += 40;
    *(_QWORD *)(a2 + 64) = v3;
    v4 += 40;
  }
  while ( v4 != a2 + 184 );
  *(_QWORD *)(a2 + 88) = v3;
  v5 = *(_QWORD *)(a2 + 120);
  *(_BYTE *)v5 = 0;
  v6 = (__int64 *)(v5 + 8);
  *(_QWORD *)(v5 + 8) = 0;
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 0;
  v7 = 0xCCCCCCCCCCCCCCCDuLL * ((v3 - *(_QWORD *)(a2 + 80)) >> 3);
  if ( v7 )
  {
    std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Buy_nonzero(v6, v7);
    *(_QWORD *)(a2 + 128) = v6;
    v8 = *v6;
    v9 = *(_QWORD *)(a2 + 80);
    v10 = *(_QWORD *)(a2 + 88);
    *(_OWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 56) = v8;
    *(_QWORD *)(a2 + 64) = v8;
    *(_QWORD *)(a2 + 72) = v6;
    while ( v9 != v10 )
    {
      std::wstring::wstring(v8, v9);
      *(_DWORD *)(v8 + 32) = *(_DWORD *)(v9 + 32);
      v8 += 40;
      *(_QWORD *)(a2 + 64) = v8;
      v9 += 40;
    }
    v6[1] = v8;
  }
  *(_DWORD *)(a2 + 48) |= 1u;
  std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(a2 + 80);
  `eh vector destructor iterator'(
    (void *)(a2 + 144),
    0x28u,
    1u,
    std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>);
  return 0;
}

```

## disassembly

```asm
0x1400221fb  mov     [rsp+arg_8], rdx
0x140022200  push    rbx
0x140022201  push    rbp
0x140022202  push    rsi
0x140022203  push    rdi
0x140022204  push    r14
0x140022206  sub     rsp, 30h
0x14002220a  mov     rbp, rdx
0x14002220d  xorps   xmm0, xmm0
0x140022210  movups  xmmword ptr [rbp+90h], xmm0
0x140022217  mov     qword ptr [rbp+0A0h], 0
0x140022222  mov     qword ptr [rbp+0A8h], 0
0x14002222d  mov     r8d, 1
0x140022233  lea     rdx, asc_140027804; "$"
0x14002223a  lea     rcx, [rbp+90h]
0x140022241  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140022246  mov     dword ptr [rbp+0B0h], 0Dh
0x140022250  xorps   xmm0, xmm0
0x140022253  movdqu  xmmword ptr [rbp+50h], xmm0
0x140022258  mov     qword ptr [rbp+60h], 0
0x140022260  mov     edx, 1
0x140022265  lea     rcx, [rbp+50h]
0x140022269  call    ?_Buy_nonzero@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Buy_nonzero(unsigned __int64)
0x14002226e  lea     rax, [rbp+50h]
0x140022272  mov     [rbp+80h], rax
0x140022279  mov     rbx, [rbp+50h]
0x14002227d  lea     rdi, [rbp+90h]
0x140022284  xorps   xmm0, xmm0
0x140022287  movups  xmmword ptr [rbp+38h], xmm0
0x14002228b  mov     [rbp+38h], rbx
0x14002228f  mov     [rbp+40h], rbx
0x140022293  lea     rax, [rbp+50h]
0x140022297  mov     [rbp+48h], rax
0x14002229b  mov     rdx, rdi
0x14002229e  mov     rcx, rbx
0x1400222a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400222a6  mov     eax, [rdi+20h]
0x1400222a9  mov     [rbx+20h], eax
0x1400222ac  add     rbx, 28h ; '('
0x1400222b0  mov     [rbp+40h], rbx
0x1400222b4  add     rdi, 28h ; '('
0x1400222b8  lea     rax, [rbp+0B8h]
0x1400222bf  cmp     rdi, rax
0x1400222c2  jnz     short loc_14002229B
0x1400222c4  mov     [rbp+58h], rbx
0x1400222c8  mov     rax, [rbp+78h]
0x1400222cc  mov     byte ptr [rax], 0
0x1400222cf  lea     rdi, [rax+8]
0x1400222d3  mov     qword ptr [rdi], 0
0x1400222da  mov     qword ptr [rdi+8], 0
0x1400222e2  mov     qword ptr [rdi+10h], 0
0x1400222ea  sub     rbx, [rbp+50h]
0x1400222ee  sar     rbx, 3
0x1400222f2  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400222fc  imul    rbx, rax
0x140022300  test    rbx, rbx
0x140022303  jz      short loc_14002235D
0x140022305  mov     rdx, rbx
0x140022308  mov     rcx, rdi
0x14002230b  call    ?_Buy_nonzero@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Buy_nonzero(unsigned __int64)
0x140022310  mov     [rbp+80h], rdi
0x140022317  mov     rbx, [rdi]
0x14002231a  mov     rsi, [rbp+50h]
0x14002231e  mov     r14, [rbp+58h]
0x140022322  xorps   xmm0, xmm0
0x140022325  movups  xmmword ptr [rbp+38h], xmm0
0x140022329  mov     [rbp+38h], rbx
0x14002232d  mov     [rbp+40h], rbx
0x140022331  mov     [rbp+48h], rdi
0x140022335  jmp     short loc_140022354
0x140022337  mov     rdx, rsi
0x14002233a  mov     rcx, rbx
0x14002233d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140022342  mov     eax, [rsi+20h]
0x140022345  mov     [rbx+20h], eax
0x140022348  add     rbx, 28h ; '('
0x14002234c  mov     [rbp+40h], rbx
0x140022350  add     rsi, 28h ; '('
0x140022354  cmp     rsi, r14
0x140022357  jnz     short loc_140022337
0x140022359  mov     [rdi+8], rbx
0x14002235d  or      dword ptr [rbp+30h], 1
0x140022361  lea     rcx, [rbp+50h]
0x140022365  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x14002236a  nop
0x14002236b  lea     r9, ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; void (*)(void *)
0x140022372  mov     edx, 28h ; '('; unsigned __int64
0x140022377  lea     r8d, [rdx-27h]; unsigned __int64
0x14002237b  lea     rcx, [rbp+90h]; void *
0x140022382  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x140022387  nop
0x140022388  mov     rax, 0
0x140022392  add     rsp, 30h
0x140022396  pop     r14
0x140022398  pop     rdi
0x140022399  pop     rsi
0x14002239a  pop     rbp
0x14002239b  pop     rbx
0x14002239c  retn
```
