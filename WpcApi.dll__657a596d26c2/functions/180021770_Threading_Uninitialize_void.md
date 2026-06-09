# Threading::Uninitialize(void)

- ea: `0x180021770`
- end: `0x180021a78`
- name: `?Uninitialize@Threading@@YAXXZ`
- size: `776`
- prototype: `void __fastcall(Threading *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000a2c0`

## callees

- `0x18000b29c`
- `0x180021304`
- `0x1800214b4`
- `0x180021770`
- `0x180021e10`
- `0x180021e58`
- `0x18002c010`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x1800217e7`
- `KERNEL32!TlsGetValue` at `0x180021804`
- `KERNEL32!TlsGetValue` at `0x1800217e7`
- `KERNEL32!TlsGetValue` at `0x180021804`
- `KERNEL32!Sleep` at `0x180021982`
- `KERNEL32!Sleep` at `0x180021982`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Threading::Uninitialize(Threading *this)
{
  int v1; // r14d
  unsigned __int64 v2; // rsi
  __int64 v3; // rax
  __int64 v4; // rdx
  unsigned __int64 i; // r8
  _QWORD *v6; // rbx
  _QWORD *Value; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  _QWORD *v11; // rdi
  _QWORD *v12; // rdi
  _QWORD *j; // rbx
  unsigned int v14; // edi
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // r15
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 ***v26; // rdi
  __int64 **k; // rbx
  __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  _QWORD *v29; // [rsp+38h] [rbp-28h]
  _QWORD v30[4]; // [rsp+40h] [rbp-20h] BYREF

  v30[2] = &off_1800442B8;
  v30[3] = &qword_1800442C8;
  ((void (*)(void))off_1800442B8[2])();
  v1 = 2;
  byte_18004ABB0 = 0;
  v2 = 0;
  v3 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v28);
  if ( TlsGetValue(dword_18004A6D8) )
  {
    v6 = v29;
    Value = TlsGetValue(dword_18004A6D8);
    v8 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 8; ++i )
      v8 = 0x100000001B3LL * (*((unsigned __int8 *)Value + i) ^ (unsigned __int64)v8);
    v9 = 2 * (v8 & v6[6]);
    v4 = v6[3];
    v10 = *(_QWORD *)(v4 + 8 * v9 + 8);
    if ( v10 == v6[1] )
    {
LABEL_9:
      v10 = 0;
    }
    else
    {
      i = *(_QWORD *)(v4 + 8 * v9);
      while ( *Value != *(_QWORD *)(v10 + 16) )
      {
        if ( v10 == i )
          goto LABEL_9;
        v10 = *(_QWORD *)(v10 + 8);
      }
    }
    if ( !v10 )
      v10 = v6[1];
    v11 = v29;
    if ( v10 != v29[1] )
      v2 = 1;
  }
  else
  {
    v11 = v29;
  }
  v12 = (_QWORD *)v11[1];
  for ( j = (_QWORD *)*v12; j != v12; j = (_QWORD *)*j )
    anonymous_namespace_::CancelThread(j[3]);
  if ( v28 )
    (*(void (__fastcall **)(__int64, __int64, unsigned __int64))(*(_QWORD *)v28 + 24LL))(v28, v4, i);
  v14 = 0;
  v15 = v28;
  do
  {
    v16 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
    v17 = *(_QWORD *)(*(_QWORD *)((*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v16 + 40LL))(v16, v30) + 8)
                    + 16LL);
    if ( v30[0] )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30[0] + 8LL))(v30[0]);
      v30[0] = 0;
    }
    if ( v17 <= v2 )
      break;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      v18 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
      v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 40LL))(v18, &v28);
      v1 |= 1u;
      WPP_SF_P(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v20, v21, *(_QWORD *)(*(_QWORD *)(v19 + 8) + 16LL));
      v15 = v28;
    }
    if ( (v1 & 1) != 0 )
    {
      v1 &= ~1u;
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        v15 = 0;
        v28 = 0;
      }
    }
    Sleep(0x1F4u);
    ++v14;
  }
  while ( v14 < 0xA );
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v22 = Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->();
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 40LL))(v22, &v28);
    v25 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    {
      WPP_SF_PP(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v23, v24, v29[2], v2);
      v25 = WPP_GLOBAL_Control;
    }
    v26 = (__int64 ***)v29[1];
    for ( k = *v26; k != (__int64 **)v26; k = (__int64 **)*k )
    {
      if ( (_UNKNOWN *)v25 != &WPP_GLOBAL_Control && (*(_BYTE *)(v25 + 28) & 8) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(v25 + 16), 16, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids, *(unsigned int *)k[3]);
        v25 = WPP_GLOBAL_Control;
      }
    }
    if ( v28 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
  }
  ((void (__fastcall *)(void ***))off_1800442B8[3])(&off_1800442B8);
}

```

## disassembly

```asm
0x180021770  mov     [rsp-28h+arg_8], rbx
0x180021775  mov     [rsp-28h+arg_10], rsi
0x18002177a  push    rbp
0x18002177b  push    rdi
0x18002177c  push    r13
0x18002177e  push    r14
0x180021780  push    r15
0x180021782  mov     rbp, rsp
0x180021785  sub     rsp, 60h
0x180021789  mov     [rbp+arg_0], 0
0x180021790  lea     rcx, off_1800442B8
0x180021797  mov     [rbp+var_10], rcx
0x18002179b  lea     rax, qword_1800442C8
0x1800217a2  mov     [rbp+var_8], rax
0x1800217a6  mov     rax, cs:off_1800442B8
0x1800217ad  mov     rax, [rax+10h]
0x1800217b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217b6  mov     r14d, 2
0x1800217bc  mov     cs:byte_18004ABB0, 0
0x1800217c3  xor     esi, esi
0x1800217c5  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x1800217ca  mov     r8, rax
0x1800217cd  mov     rcx, [rax]
0x1800217d0  mov     rax, [rcx+30h]
0x1800217d4  lea     rdx, [rbp+var_30]
0x1800217d8  mov     rcx, r8
0x1800217db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217e0  nop
0x1800217e1  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x1800217e7  call    cs:__imp_TlsGetValue
0x1800217ed  lea     r15d, [r14-1]
0x1800217f1  test    rax, rax
0x1800217f4  jz      loc_180021882
0x1800217fa  mov     rbx, [rbp+var_28]
0x1800217fe  mov     ecx, cs:dword_18004A6D8; dwTlsIndex
0x180021804  call    cs:__imp_TlsGetValue
0x18002180a  mov     r9, rax
0x18002180d  mov     rdx, 0CBF29CE484222325h
0x180021817  xor     r8d, r8d
0x18002181a  movzx   ecx, byte ptr [r9+r8]
0x18002181f  xor     rdx, rcx
0x180021822  mov     rax, 100000001B3h
0x18002182c  imul    rdx, rax
0x180021830  add     r8, r15
0x180021833  cmp     r8, 8
0x180021837  jb      short loc_18002181A
0x180021839  mov     rcx, [rbx+30h]
0x18002183d  and     rcx, rdx
0x180021840  add     rcx, rcx
0x180021843  mov     rdx, [rbx+18h]
0x180021847  mov     rax, [rdx+rcx*8+8]
0x18002184c  cmp     rax, [rbx+8]
0x180021850  jz      short loc_18002186A
0x180021852  mov     r8, [rdx+rcx*8]
0x180021856  mov     rcx, [r9]
0x180021859  cmp     rcx, [rax+10h]
0x18002185d  jz      short loc_18002186C
0x18002185f  cmp     rax, r8
0x180021862  jz      short loc_18002186A
0x180021864  mov     rax, [rax+8]
0x180021868  jmp     short loc_180021859
0x18002186a  xor     eax, eax
0x18002186c  test    rax, rax
0x18002186f  cmovz   rax, [rbx+8]
0x180021874  mov     rdi, [rbp+var_28]
0x180021878  cmp     rax, [rdi+8]
0x18002187c  cmovnz  rsi, r15
0x180021880  jmp     short loc_180021886
0x180021882  mov     rdi, [rbp+var_28]
0x180021886  mov     rdi, [rdi+8]
0x18002188a  mov     rbx, [rdi]
0x18002188d  cmp     rbx, rdi
0x180021890  jz      short loc_1800218A0
0x180021892  mov     rcx, [rbx+18h]
0x180021896  call    _anonymous_namespace___CancelThread
0x18002189b  mov     rbx, [rbx]
0x18002189e  jmp     short loc_18002188D
0x1800218a0  mov     rcx, [rbp+var_30]
0x1800218a4  test    rcx, rcx
0x1800218a7  jz      short loc_1800218B6
0x1800218a9  mov     rax, [rcx]
0x1800218ac  mov     rax, [rax+18h]
0x1800218b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218b5  nop
0x1800218b6  xor     edi, edi
0x1800218b8  lea     r13, WPP_GLOBAL_Control
0x1800218bf  mov     rbx, [rbp+var_30]
0x1800218c3  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x1800218c8  mov     r8, rax
0x1800218cb  mov     rcx, [rax]
0x1800218ce  mov     rax, [rcx+28h]
0x1800218d2  lea     rdx, [rbp+var_20]
0x1800218d6  mov     rcx, r8
0x1800218d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218de  mov     rcx, [rax+8]
0x1800218e2  mov     r15, [rcx+10h]
0x1800218e6  mov     rcx, [rbp+var_20]
0x1800218ea  test    rcx, rcx
0x1800218ed  jz      short loc_180021903
0x1800218ef  mov     rax, [rcx]
0x1800218f2  mov     rax, [rax+8]
0x1800218f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218fb  mov     [rbp+var_20], 0
0x180021903  cmp     r15, rsi
0x180021906  jbe     loc_180021993
0x18002190c  mov     rax, cs:WPP_GLOBAL_Control
0x180021913  cmp     rax, r13
0x180021916  jz      short loc_180021959
0x180021918  test    byte ptr [rax+1Ch], 8
0x18002191c  jz      short loc_180021959
0x18002191e  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x180021923  mov     r8, rax
0x180021926  mov     rcx, [rax]
0x180021929  mov     rax, [rcx+28h]
0x18002192d  lea     rdx, [rbp+var_30]
0x180021931  mov     rcx, r8
0x180021934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021939  or      r14d, 1
0x18002193d  mov     r9, [rax+8]
0x180021941  mov     r9, [r9+10h]
0x180021945  mov     rcx, cs:WPP_GLOBAL_Control
0x18002194c  mov     rcx, [rcx+10h]
0x180021950  call    WPP_SF_P
0x180021955  mov     rbx, [rbp+var_30]
0x180021959  test    r14b, 1
0x18002195d  jz      short loc_18002197D
0x18002195f  and     r14d, 0FFFFFFFEh
0x180021963  test    rbx, rbx
0x180021966  jz      short loc_18002197D
0x180021968  mov     rax, [rbx]
0x18002196b  mov     rcx, rbx
0x18002196e  mov     rax, [rax+8]
0x180021972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021977  xor     ebx, ebx
0x180021979  mov     [rbp+var_30], rbx
0x18002197d  mov     ecx, 1F4h; dwMilliseconds
0x180021982  call    cs:__imp_Sleep
0x180021988  inc     edi
0x18002198a  cmp     edi, 0Ah
0x18002198d  jb      loc_1800218C3
0x180021993  mov     rax, cs:WPP_GLOBAL_Control
0x18002199a  test    byte ptr [rax+1Ch], 4
0x18002199e  jz      loc_180021A47
0x1800219a4  call    ??C?$Global@V?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@@@QEAAPEAV?$LockBox@V?$unordered_map@_KPEAUThreadInfo@Private@@U?$hash@_K@std@@U?$equal_to@_K@4@V?$allocator@U?$pair@$$CB_KPEAUThreadInfo@Private@@@std@@@4@@std@@$0PPPPPPPP@@@XZ; Global<LockBox<std::unordered_map<unsigned __int64,Private::ThreadInfo *>,4294967295>>::operator->(void)
0x1800219a9  mov     r8, rax
0x1800219ac  mov     rcx, [rax]
0x1800219af  mov     rax, [rcx+28h]
0x1800219b3  lea     rdx, [rbp+var_30]
0x1800219b7  mov     rcx, r8
0x1800219ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800219bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219c6  cmp     rcx, r13
0x1800219c9  jz      short loc_1800219EE
0x1800219cb  test    byte ptr [rcx+1Ch], 8
0x1800219cf  jz      short loc_1800219EE
0x1800219d1  mov     [rsp+60h+var_40], rsi
0x1800219d6  mov     r9, [rbp+var_28]
0x1800219da  mov     r9, [r9+10h]
0x1800219de  mov     rcx, [rcx+10h]
0x1800219e2  call    WPP_SF_PP
0x1800219e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219ee  mov     rdi, [rbp+var_28]
0x1800219f2  mov     rdi, [rdi+8]
0x1800219f6  mov     rbx, [rdi]
0x1800219f9  cmp     rbx, rdi
0x1800219fc  jz      short loc_180021A31
0x1800219fe  cmp     rcx, r13
0x180021a01  jz      short loc_180021A2C
0x180021a03  test    byte ptr [rcx+1Ch], 8
0x180021a07  jz      short loc_180021A2C
0x180021a09  mov     r9, [rbx+18h]
0x180021a0d  mov     edx, 10h
0x180021a12  mov     r9d, [r9]
0x180021a15  lea     r8, WPP_8f71bf2a86f63c0585a15c2236b3f2b4_Traceguids
0x180021a1c  mov     rcx, [rcx+10h]
0x180021a20  call    WPP_SF_d
0x180021a25  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a2c  mov     rbx, [rbx]
0x180021a2f  jmp     short loc_1800219F9
0x180021a31  mov     rcx, [rbp+var_30]
0x180021a35  test    rcx, rcx
0x180021a38  jz      short loc_180021A47
0x180021a3a  mov     rax, [rcx]
0x180021a3d  mov     rax, [rax+8]
0x180021a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a46  nop
0x180021a47  mov     rax, cs:off_1800442B8
0x180021a4e  lea     rcx, off_1800442B8
0x180021a55  mov     rax, [rax+18h]
0x180021a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a5e  nop
0x180021a5f  lea     r11, [rsp+60h+var_s0]
0x180021a64  mov     rbx, [r11+38h]
0x180021a68  mov     rsi, [r11+40h]
0x180021a6c  mov     rsp, r11
0x180021a6f  pop     r15
0x180021a71  pop     r14
0x180021a73  pop     r13
0x180021a75  pop     rdi
0x180021a76  pop     rbp
0x180021a77  retn
```
