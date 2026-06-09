# FrameWindow::CreateTabFromId(PluginId)

- ea: `0x180021e24`
- end: `0x1800221fd`
- name: `?CreateTabFromId@FrameWindow@@AEAAJW4PluginId@@@Z`
- size: `985`
- prototype: `__int64 __fastcall(__int64, signed int)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180023660`
- `0x180025cac`
- `0x18002620c`
- `0x180026d04`
- `0x180028a60`
- `0x1800290f4`

## callees

- `0x180003858`
- `0x180021764`
- `0x1800219b4`
- `0x180021e24`
- `0x180031ec0`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800220c4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800220c4`
- `OLEAUT32!__imp_SysFreeString` at `0x180022068`
- `OLEAUT32!__imp_SysFreeString` at `0x180022068`

## pseudocode

```c
__int64 __fastcall FrameWindow::CreateTabFromId(__int64 a1, signed int a2)
{
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v6; // rcx
  char v7; // r12
  __int64 *v8; // rax
  _DWORD *i; // rax
  int ScriptToolInitializeInfo; // ebx
  _QWORD *v12; // rdx
  volatile signed __int32 *v13; // rdx
  unsigned __int16 v14; // si
  unsigned __int16 v15; // bp
  const OLECHAR *v16; // r13
  OLECHAR *v17; // rbx
  __int64 v18; // rsi
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rax
  _BYTE v24[8]; // [rsp+20h] [rbp-68h] BYREF
  __int64 v25; // [rsp+28h] [rbp-60h]
  __int64 v26; // [rsp+30h] [rbp-58h]

  v4 = *(_QWORD *)(a1 + 448);
  v5 = *(_QWORD *)(v4 + 8);
  HIDWORD(v25) = 0;
  v6 = v4;
  v7 = 0;
  while ( !*(_BYTE *)(v5 + 25) )
  {
    if ( *(_DWORD *)(v5 + 32) >= a2 )
      v6 = v5;
    v8 = (__int64 *)(v5 + 16);
    if ( *(_DWORD *)(v5 + 32) >= a2 )
      v8 = (__int64 *)v5;
    v5 = *v8;
  }
  if ( !*(_BYTE *)(v6 + 25) && a2 >= *(_DWORD *)(v6 + 32) && v6 != v4 || FrameWindow::s_isDestroying )
    return 0;
  if ( a2 == 8 )
    return FrameWindow::CreatePopup((FrameWindow *)a1);
  for ( i = *(_DWORD **)(a1 + 480); ; ++i )
  {
    if ( i == *(_DWORD **)(a1 + 488) )
      return 2147947423LL;
    if ( *i == a2 )
      break;
  }
  v25 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v26 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  ScriptToolInitializeInfo = F12::GetScriptToolInitializeInfo((unsigned int)a2, v24);
  if ( ScriptToolInitializeInfo )
  {
    if ( ScriptToolInitializeInfo >= 0 )
      ScriptToolInitializeInfo = -2147467259;
    v12 = (_QWORD *)(v26 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v26 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
    v13 = (volatile signed __int32 *)(v25 - 24);
LABEL_25:
    if ( _InterlockedDecrement(v13 + 4) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
    return (unsigned int)ScriptToolInitializeInfo;
  }
  switch ( a2 )
  {
    case 1:
      v14 = 911;
      v15 = 931;
      break;
    case 2:
      v14 = 913;
      v15 = 933;
      break;
    case 3:
      v14 = 915;
      v15 = 935;
      break;
    case 4:
      v14 = 917;
      v15 = 937;
      break;
    case 5:
      v14 = 921;
      v15 = 941;
      break;
    case 6:
      v14 = 923;
      v15 = 943;
      break;
    case 9:
      v14 = 907;
      v15 = 927;
      break;
    default:
      v14 = 0;
      v15 = 0;
      break;
  }
  v16 = (const OLECHAR *)v25;
  if ( *(_DWORD *)(a1 + 544) == -1 )
  {
    *(_DWORD *)(a1 + 544) = a2;
    if ( v16 )
    {
      v17 = SysAllocString(v16);
      if ( !v17 )
        ATL::AtlThrowImpl(-2147024882);
    }
    else
    {
      v17 = 0;
    }
    (*(void (__fastcall **)(_QWORD, __int64, OLECHAR *))(**(_QWORD **)(a1 + 568) + 48LL))(
      *(_QWORD *)(a1 + 568),
      903,
      v17);
    if ( v15 )
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 568) + 48LL))(*(_QWORD *)(a1 + 568), v15, 0);
      v7 = 1;
    }
    SysFreeString(v17);
  }
  if ( v14 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 + 568) + 48LL))(*(_QWORD *)(a1 + 568), v14, 0);
  v18 = v26;
  ScriptToolInitializeInfo = FrameWindow::CreateScriptTab(a1, a2, (__int64)v16, v26);
  if ( v7 )
  {
    v19 = *(_QWORD *)(a1 + 448);
    v20 = *(_QWORD *)(v19 + 8);
    HIDWORD(v25) = 0;
    v21 = v19;
    while ( !*(_BYTE *)(v20 + 25) )
    {
      if ( *(_DWORD *)(v20 + 32) >= a2 )
        v21 = v20;
      v22 = (__int64 *)(v20 + 16);
      if ( *(_DWORD *)(v20 + 32) >= a2 )
        v22 = (__int64 *)v20;
      v20 = *v22;
    }
    if ( !*(_BYTE *)(v21 + 25) && a2 >= *(_DWORD *)(v21 + 32) && v21 != v19 )
    {
      v23 = *(_QWORD *)(v21 + 40);
      if ( v23 )
        *(_BYTE *)(v23 + 26) = 1;
    }
  }
  if ( ScriptToolInitializeInfo != -2147483622 )
  {
    if ( ScriptToolInitializeInfo )
    {
      if ( ScriptToolInitializeInfo >= 0 )
        ScriptToolInitializeInfo = -2147467259;
      if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 - 24) + 8LL))(*(_QWORD *)(v18 - 24));
      v13 = (volatile signed __int32 *)(v16 - 12);
      goto LABEL_25;
    }
    if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 - 24) + 8LL))(*(_QWORD *)(v18 - 24));
    if ( _InterlockedDecrement((volatile signed __int32 *)v16 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
    return 0;
  }
  if ( _InterlockedDecrement((volatile signed __int32 *)(v18 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v18 - 24) + 8LL))(*(_QWORD *)(v18 - 24));
  if ( _InterlockedDecrement((volatile signed __int32 *)v16 - 2) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v16 - 3) + 8LL))(*((_QWORD *)v16 - 3));
  return 2147483674LL;
}

```

## disassembly

```asm
0x180021e24  push    rbx
0x180021e26  push    rbp
0x180021e27  push    rsi
0x180021e28  push    rdi
0x180021e29  push    r12
0x180021e2b  push    r13
0x180021e2d  push    r14
0x180021e2f  push    r15
0x180021e31  sub     rsp, 48h
0x180021e35  mov     r14d, edx
0x180021e38  mov     r15, rcx
0x180021e3b  mov     r8, [rcx+1C0h]
0x180021e42  mov     rdx, [r8+8]
0x180021e46  xor     eax, eax
0x180021e48  mov     [rsp+88h+var_5C], eax
0x180021e4c  mov     rcx, r8
0x180021e4f  xor     r12d, r12d
0x180021e52  jmp     short loc_180021E67
0x180021e54  cmp     [rdx+20h], r14d
0x180021e58  cmovge  rcx, rdx
0x180021e5c  lea     rax, [rdx+10h]
0x180021e60  cmovge  rax, rdx
0x180021e64  mov     rdx, [rax]
0x180021e67  cmp     [rdx+19h], r12b
0x180021e6b  jz      short loc_180021E54
0x180021e6d  cmp     [rcx+19h], r12b
0x180021e71  jnz     short loc_180021E82
0x180021e73  cmp     r14d, [rcx+20h]
0x180021e77  jl      short loc_180021E82
0x180021e79  cmp     rcx, r8
0x180021e7c  jnz     loc_1800221DF
0x180021e82  cmp     cs:?s_isDestroying@FrameWindow@@2_NA, r12b; bool FrameWindow::s_isDestroying
0x180021e89  jnz     loc_1800221DF
0x180021e8f  cmp     r14d, 8
0x180021e93  jnz     short loc_180021EA2
0x180021e95  mov     rcx, r15; this
0x180021e98  call    ?CreatePopup@FrameWindow@@AEAAJXZ; FrameWindow::CreatePopup(void)
0x180021e9d  jmp     loc_1800221E1
0x180021ea2  mov     rax, [r15+1E0h]
0x180021ea9  mov     rcx, [r15+1E8h]
0x180021eb0  jmp     short loc_180021EBB
0x180021eb2  cmp     [rax], r14d
0x180021eb5  jz      short loc_180021ECA
0x180021eb7  add     rax, 4
0x180021ebb  cmp     rax, rcx
0x180021ebe  jnz     short loc_180021EB2
0x180021ec0  mov     eax, 8007139Fh
0x180021ec5  jmp     loc_1800221E1
0x180021eca  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180021ed1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180021ed8  mov     rax, [rax+18h]
0x180021edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ee1  add     rax, 18h
0x180021ee5  mov     [rsp+28h], rax
0x180021eea  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180021ef1  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180021ef8  mov     rax, [rax+18h]
0x180021efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f01  add     rax, 18h
0x180021f05  mov     [rsp+88h+var_58], rax
0x180021f0a  lea     rdx, [rsp+88h+var_68]
0x180021f0f  mov     ecx, r14d
0x180021f12  call    ?GetScriptToolInitializeInfo@F12@@YAJW4PluginId@@AEAUScriptToolInitializeInfo@@@Z; F12::GetScriptToolInitializeInfo(PluginId,ScriptToolInitializeInfo &)
0x180021f17  mov     ebx, eax
0x180021f19  test    eax, eax
0x180021f1b  jz      short loc_180021F7B
0x180021f1d  mov     eax, 80004005h
0x180021f22  test    ebx, ebx
0x180021f24  cmovns  ebx, eax
0x180021f27  mov     rdx, [rsp+88h+var_58]
0x180021f2c  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180021f30  or      edi, 0FFFFFFFFh
0x180021f33  mov     eax, edi
0x180021f35  lock xadd [rdx+10h], eax
0x180021f3a  add     eax, edi
0x180021f3c  test    eax, eax
0x180021f3e  jg      short loc_180021F4F
0x180021f40  mov     rcx, [rdx]
0x180021f43  mov     rax, [rcx]
0x180021f46  mov     rax, [rax+8]
0x180021f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f4f  mov     rdx, [rsp+28h]
0x180021f54  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180021f58  mov     ecx, edi
0x180021f5a  lock xadd [rdx+10h], ecx
0x180021f5f  add     ecx, edi
0x180021f61  test    ecx, ecx
0x180021f63  jg      short loc_180021F74
0x180021f65  mov     rcx, [rdx]
0x180021f68  mov     r8, [rcx]
0x180021f6b  mov     rax, [r8+8]
0x180021f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f74  mov     eax, ebx
0x180021f76  jmp     loc_1800221E1
0x180021f7b  mov     ecx, r14d
0x180021f7e  sub     ecx, 1
0x180021f81  jz      short loc_180021FF4
0x180021f83  sub     ecx, 1
0x180021f86  jz      short loc_180021FEA
0x180021f88  sub     ecx, 1
0x180021f8b  jz      short loc_180021FE0
0x180021f8d  sub     ecx, 1
0x180021f90  jz      short loc_180021FD6
0x180021f92  sub     ecx, 1
0x180021f95  jz      short loc_180021FCC
0x180021f97  sub     ecx, 1
0x180021f9a  jz      short loc_180021FC2
0x180021f9c  sub     ecx, 2
0x180021f9f  jz      short loc_180021FB8
0x180021fa1  cmp     ecx, 1
0x180021fa4  jz      short loc_180021FAE
0x180021fa6  mov     esi, r12d
0x180021fa9  mov     ebp, r12d
0x180021fac  jmp     short loc_180021FFC
0x180021fae  mov     esi, 38Bh
0x180021fb3  lea     ebp, [rsi+14h]
0x180021fb6  jmp     short loc_180021FFC
0x180021fb8  mov     esi, 39Dh
0x180021fbd  lea     ebp, [rsi+0Eh]
0x180021fc0  jmp     short loc_180021FFC
0x180021fc2  mov     esi, 39Bh
0x180021fc7  lea     ebp, [rsi+14h]
0x180021fca  jmp     short loc_180021FFC
0x180021fcc  mov     esi, 399h
0x180021fd1  lea     ebp, [rsi+14h]
0x180021fd4  jmp     short loc_180021FFC
0x180021fd6  mov     esi, 395h
0x180021fdb  lea     ebp, [rsi+14h]
0x180021fde  jmp     short loc_180021FFC
0x180021fe0  mov     esi, 393h
0x180021fe5  lea     ebp, [rsi+14h]
0x180021fe8  jmp     short loc_180021FFC
0x180021fea  mov     esi, 391h
0x180021fef  lea     ebp, [rsi+14h]
0x180021ff2  jmp     short loc_180021FFC
0x180021ff4  mov     esi, 38Fh
0x180021ff9  lea     ebp, [rsi+14h]
0x180021ffc  mov     r13, [rsp+28h]
0x180022001  or      edi, 0FFFFFFFFh
0x180022004  cmp     [r15+220h], edi
0x18002200b  jnz     short loc_18002206E
0x18002200d  mov     [r15+220h], r14d
0x180022014  xor     eax, eax
0x180022016  test    r13, r13
0x180022019  jnz     loc_1800220C1
0x18002201f  mov     ebx, eax
0x180022021  mov     [rsp+88h+arg_0], rax
0x180022029  mov     rcx, [r15+238h]
0x180022030  mov     rax, [rcx]
0x180022033  mov     r8, rbx
0x180022036  mov     edx, 387h
0x18002203b  mov     rax, [rax+30h]
0x18002203f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022044  test    bp, bp
0x180022047  jz      short loc_180022065
0x180022049  mov     rcx, [r15+238h]
0x180022050  mov     rax, [rcx]
0x180022053  movzx   edx, bp
0x180022056  xor     r8d, r8d
0x180022059  mov     rax, [rax+30h]
0x18002205d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022062  mov     r12b, 1
0x180022065  mov     rcx, rbx; bstrString
0x180022068  call    cs:__imp_SysFreeString
0x18002206e  xor     ebp, ebp
0x180022070  test    si, si
0x180022073  jz      short loc_18002208E
0x180022075  mov     rcx, [r15+238h]
0x18002207c  mov     rax, [rcx]
0x18002207f  movzx   edx, si
0x180022082  xor     r8d, r8d
0x180022085  mov     rax, [rax+30h]
0x180022089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002208e  mov     rsi, [rsp+88h+var_58]
0x180022093  mov     r9, rsi
0x180022096  mov     r8, r13
0x180022099  mov     edx, r14d
0x18002209c  mov     rcx, r15
0x18002209f  call    ?CreateScriptTab@FrameWindow@@AEAAJW4PluginId@@PEBG1@Z; FrameWindow::CreateScriptTab(PluginId,ushort const *,ushort const *)
0x1800220a4  mov     ebx, eax
0x1800220a6  test    r12b, r12b
0x1800220a9  jz      short loc_18002211A
0x1800220ab  mov     r8, [r15+1C0h]
0x1800220b2  mov     rdx, [r8+8]
0x1800220b6  xor     eax, eax
0x1800220b8  mov     [rsp+88h+var_5C], eax
0x1800220bc  mov     rcx, r8
0x1800220bf  jmp     short loc_1800220F6
0x1800220c1  mov     rcx, r13; psz
0x1800220c4  call    cs:__imp_SysAllocString
0x1800220ca  mov     rbx, rax
0x1800220cd  mov     [rsp+88h+arg_0], rax
0x1800220d5  test    rax, rax
0x1800220d8  jz      loc_1800221F2
0x1800220de  jmp     loc_180022029
0x1800220e3  cmp     [rdx+20h], r14d
0x1800220e7  cmovge  rcx, rdx
0x1800220eb  lea     rax, [rdx+10h]
0x1800220ef  cmovge  rax, rdx
0x1800220f3  mov     rdx, [rax]
0x1800220f6  cmp     [rdx+19h], bpl
0x1800220fa  jz      short loc_1800220E3
0x1800220fc  cmp     [rcx+19h], bpl
0x180022100  jnz     short loc_18002211A
0x180022102  cmp     r14d, [rcx+20h]
0x180022106  jl      short loc_18002211A
0x180022108  cmp     rcx, r8
0x18002210b  jz      short loc_18002211A
0x18002210d  mov     rax, [rcx+28h]
0x180022111  test    rax, rax
0x180022114  jz      short loc_18002211A
0x180022116  mov     byte ptr [rax+1Ah], 1
0x18002211a  mov     r14d, 8000001Ah
0x180022120  cmp     ebx, r14d
0x180022123  jnz     short loc_18002216A
0x180022125  lea     rdx, [rsi-18h]
0x180022129  mov     eax, edi
0x18002212b  lock xadd [rdx+10h], eax
0x180022130  add     eax, edi
0x180022132  test    eax, eax
0x180022134  jg      short loc_180022145
0x180022136  mov     rcx, [rdx]
0x180022139  mov     rax, [rcx]
0x18002213c  mov     rax, [rax+8]
0x180022140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022145  lea     rdx, [r13-18h]
0x180022149  mov     ecx, edi
0x18002214b  lock xadd [rdx+10h], ecx
0x180022150  add     ecx, edi
0x180022152  test    ecx, ecx
0x180022154  jg      short loc_180022165
0x180022156  mov     rcx, [rdx]
0x180022159  mov     r8, [rcx]
0x18002215c  mov     rax, [r8+8]
0x180022160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022165  mov     eax, r14d
0x180022168  jmp     short loc_1800221E1
0x18002216a  test    ebx, ebx
0x18002216c  jz      short loc_18002219F
0x18002216e  mov     eax, 80004005h
0x180022173  cmovns  ebx, eax
0x180022176  lea     rdx, [rsi-18h]
0x18002217a  mov     eax, edi
0x18002217c  lock xadd [rdx+10h], eax
0x180022181  add     eax, edi
0x180022183  test    eax, eax
0x180022185  jg      short loc_180022196
0x180022187  mov     rcx, [rdx]
0x18002218a  mov     rax, [rcx]
0x18002218d  mov     rax, [rax+8]
0x180022191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022196  lea     rdx, [r13-18h]
0x18002219a  jmp     loc_180021F58
0x18002219f  lea     rdx, [rsi-18h]
0x1800221a3  mov     eax, edi
0x1800221a5  lock xadd [rdx+10h], eax
0x1800221aa  add     eax, edi
0x1800221ac  test    eax, eax
0x1800221ae  jg      short loc_1800221BF
0x1800221b0  mov     rcx, [rdx]
0x1800221b3  mov     rax, [rcx]
0x1800221b6  mov     rax, [rax+8]
0x1800221ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221bf  lea     rdx, [r13-18h]
0x1800221c3  mov     eax, edi
0x1800221c5  lock xadd [rdx+10h], eax
0x1800221ca  add     eax, edi
0x1800221cc  test    eax, eax
0x1800221ce  jg      short loc_1800221DF
0x1800221d0  mov     rcx, [rdx]
0x1800221d3  mov     rax, [rcx]
0x1800221d6  mov     rax, [rax+8]
0x1800221da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221df  xor     eax, eax
0x1800221e1  add     rsp, 48h
0x1800221e5  pop     r15
0x1800221e7  pop     r14
0x1800221e9  pop     r13
0x1800221eb  pop     r12
0x1800221ed  pop     rdi
0x1800221ee  pop     rsi
0x1800221ef  pop     rbp
0x1800221f0  pop     rbx
0x1800221f1  retn
0x1800221f2  mov     ecx, 8007000Eh; int
0x1800221f7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
