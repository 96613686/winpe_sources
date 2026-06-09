# Notifier::NotifyAllCaches(ushort const *,long (ICollectionNotify::*)(ushort const *))

- ea: `0x18000e330`
- end: `0x18000e5ca`
- name: `?NotifyAllCaches@Notifier@@AEAAXPEBGP8ICollectionNotify@@EAAJ0@Z@Z`
- size: `666`
- prototype: `__int64 __fastcall(Notifier *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e170`

## callees

- `0x180008938`
- `0x18000cf88`
- `0x18000e050`
- `0x18000e1f0`
- `0x18000e330`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e448`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e56f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043b19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043b29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e56f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043b19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043b29`

## string_xrefs

- `0x18000e5ad`: `com\complus\src\events\tier2\notify.cpp`

## pseudocode

```c
void __fastcall Notifier::NotifyAllCaches(Notifier *this, __int64 a2, __int64 (__fastcall *a3)(_QWORD, __int64))
{
  _QWORD *v5; // r15
  _OWORD *v6; // rsi
  int v7; // edi
  __int64 v8; // r14
  int v9; // ebx
  int j; // ebx
  _QWORD *v11; // rdi
  int v12; // eax
  __int64 v13; // rdi
  int v14; // esi
  __int64 v15; // rbx
  __int64 v16; // rdx
  __int128 v17; // xmm6
  _QWORD *v18; // rbx
  __int64 i; // rdx
  _OWORD *v20; // [rsp+28h] [rbp-90h]
  struct _GUID v21; // [rsp+60h] [rbp-58h] BYREF
  UTSemReadWriteES *v23; // [rsp+D8h] [rbp+20h]

  v5 = 0;
  v6 = 0;
  v23 = (Notifier *)((char *)this + 40);
  UTSemReadWriteES::LockRead((Notifier *)((char *)this + 40));
  v7 = 1;
  v8 = *((unsigned int *)this + 3);
  if ( (int)v8 < 0 || (unsigned __int64)(8 * v8) > 0xFFFFFFFF || (unsigned __int64)(16 * v8) > 0xFFFFFFFF )
  {
    v9 = -2147024362;
  }
  else
  {
    v5 = CoTaskMemAlloc((unsigned int)(8 * v8));
    if ( v5 )
    {
      v6 = CoTaskMemAlloc((unsigned int)(16 * v8));
      v20 = v6;
      if ( v6 )
      {
        v13 = -(__int64)(*((_DWORD *)this + 3) != 0);
        v14 = 0;
        while ( v13 )
        {
          v15 = v13;
          if ( v13 == -1 )
          {
            for ( i = 0; (unsigned int)i < *((_DWORD *)this + 2); i = (unsigned int)(i + 1) )
            {
              v15 = *(_QWORD *)(*(_QWORD *)this + 8 * i);
              if ( v15 )
                break;
            }
          }
          v13 = *(_QWORD *)v15;
          if ( !*(_QWORD *)v15 )
          {
            LODWORD(v16) = *(_DWORD *)(v15 + 8);
            do
            {
              v16 = (unsigned int)(v16 + 1);
              if ( (unsigned int)v16 >= *((_DWORD *)this + 2) )
                break;
              v13 = *(_QWORD *)(*(_QWORD *)this + 8 * v16);
            }
            while ( !v13 );
          }
          v17 = *(_OWORD *)(v15 + 12);
          v18 = *(_QWORD **)(v15 + 32);
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v18 + 8LL))(*v18);
          v5[v14] = *v18;
          v20[v14++] = v17;
        }
        UTSemReadWriteES::UnlockRead((Notifier *)((char *)this + 40));
        for ( j = 0; j < (int)v8; ++j )
        {
          v11 = &v5[j];
          v12 = a3(*v11, a2);
          if ( v12 == -2147023174 || v12 == -2147417848 || (unsigned int)(v12 + 2147023170) <= 1 )
          {
            v21 = (struct _GUID)v20[j];
            Notifier::RemoveCache(this, &v21);
          }
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 16LL))(*v11);
        }
        v9 = 0;
        v7 = 0;
        v6 = v20;
      }
      else
      {
        v9 = -2147024882;
      }
    }
    else
    {
      v9 = -2147024882;
    }
  }
  if ( v7 )
    UTSemReadWriteES::UnlockRead(v23);
  if ( v5 )
    CoTaskMemFree(v5);
  if ( v6 )
    CoTaskMemFree(v6);
  if ( v9 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x11Bu, 0x14u, v9);
}

```

## disassembly

```asm
0x18000e330  mov     [rsp+arg_8], rdx
0x18000e335  mov     [rsp+arg_0], rcx
0x18000e33a  push    rbx
0x18000e33b  push    rsi
0x18000e33c  push    rdi
0x18000e33d  push    r12
0x18000e33f  push    r13
0x18000e341  push    r14
0x18000e343  push    r15
0x18000e345  sub     rsp, 80h
0x18000e34c  movaps  [rsp+0B8h+var_48], xmm6
0x18000e351  mov     r13, r8
0x18000e354  mov     r12, rcx
0x18000e357  xor     r15d, r15d
0x18000e35a  mov     [rsp+0B8h+var_78], r15
0x18000e35f  xor     esi, esi
0x18000e361  mov     [rsp+0B8h+var_90], rsi
0x18000e366  lea     rax, [rcx+28h]
0x18000e36a  mov     [rsp+0B8h+arg_18], rax
0x18000e372  mov     rcx, rax; this
0x18000e375  call    ?LockRead@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::LockRead(void)
0x18000e37a  mov     edi, 1
0x18000e37f  mov     [rsp+0B8h+var_94], edi
0x18000e383  mov     r14d, [r12+0Ch]
0x18000e388  test    r14d, r14d
0x18000e38b  jns     loc_18000E52E
0x18000e391  mov     ebx, 80070216h
0x18000e396  jmp     loc_18000E563
0x18000e39b  lea     rcx, [r12+28h]; this
0x18000e3a0  call    ?UnlockRead@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::UnlockRead(void)
0x18000e3a5  mov     [rsp+0B8h+var_94], 0
0x18000e3ad  xor     ebx, ebx
0x18000e3af  mov     [rsp+0B8h+var_98], ebx
0x18000e3b3  cmp     ebx, r14d
0x18000e3b6  jge     short loc_18000E3FD
0x18000e3b8  movsxd  rsi, ebx
0x18000e3bb  lea     rdi, [r15+rsi*8]
0x18000e3bf  mov     rdx, [rsp+0B8h+arg_8]
0x18000e3c7  mov     rcx, [rdi]
0x18000e3ca  mov     rax, r13
0x18000e3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3d2  cmp     eax, 800706BAh
0x18000e3d7  jz      short loc_18000E40D
0x18000e3d9  cmp     eax, 80010108h
0x18000e3de  jz      short loc_18000E40D
0x18000e3e0  add     eax, 7FF8F942h
0x18000e3e5  cmp     eax, 1
0x18000e3e8  jbe     short loc_18000E40D
0x18000e3ea  mov     rcx, [rdi]
0x18000e3ed  mov     rax, [rcx]
0x18000e3f0  mov     rax, [rax+10h]
0x18000e3f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3f9  inc     ebx
0x18000e3fb  jmp     short loc_18000E3AF
0x18000e3fd  xor     ebx, ebx
0x18000e3ff  mov     edi, [rsp+0B8h+var_94]
0x18000e403  mov     rsi, [rsp+0B8h+var_90]
0x18000e408  jmp     loc_18000E563
0x18000e40d  add     rsi, rsi
0x18000e410  mov     rax, [rsp+0B8h+var_90]
0x18000e415  movups  xmm0, xmmword ptr [rax+rsi*8]
0x18000e419  movaps  xmmword ptr [rsp+0B8h+var_58.Data1], xmm0
0x18000e41e  lea     rdx, [rsp+0B8h+var_58]; struct _GUID
0x18000e423  mov     rcx, r12; this
0x18000e426  call    ?RemoveCache@Notifier@@QEAAJU_GUID@@@Z; Notifier::RemoveCache(_GUID)
0x18000e42b  jmp     short loc_18000E3EA
0x18000e42d  mov     ecx, eax; cb
0x18000e42f  call    cs:__imp_CoTaskMemAlloc
0x18000e435  mov     r15, rax
0x18000e438  mov     [rsp+0B8h+var_78], rax
0x18000e43d  test    rax, rax
0x18000e440  jz      loc_18000E520
0x18000e446  mov     ecx, ebx; cb
0x18000e448  call    cs:__imp_CoTaskMemAlloc
0x18000e44e  mov     rsi, rax
0x18000e451  mov     [rsp+0B8h+var_90], rax
0x18000e456  test    rax, rax
0x18000e459  jz      loc_18000E527
0x18000e45f  mov     eax, [r12+0Ch]
0x18000e464  neg     eax
0x18000e466  sbb     rdi, rdi
0x18000e469  xor     esi, esi
0x18000e46b  mov     [rsp+0B8h+var_98], esi
0x18000e46f  nop
0x18000e470  test    rdi, rdi
0x18000e473  jz      loc_18000E39B
0x18000e479  mov     rbx, rdi
0x18000e47c  mov     [rsp+0B8h+var_70], rbx
0x18000e481  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000e485  jz      short loc_18000E4F9
0x18000e487  mov     [rsp+0B8h+var_80], 0
0x18000e490  mov     rdi, [rbx]
0x18000e493  mov     [rsp+0B8h+var_80], rdi
0x18000e498  test    rdi, rdi
0x18000e49b  jnz     short loc_18000E4BF
0x18000e49d  mov     edx, [rbx+8]
0x18000e4a0  inc     edx
0x18000e4a2  mov     [rsp+0B8h+var_84], edx
0x18000e4a6  cmp     edx, [r12+8]
0x18000e4ab  jnb     short loc_18000E4BF
0x18000e4ad  mov     rax, [r12]
0x18000e4b1  mov     rdi, [rax+rdx*8]
0x18000e4b5  mov     [rsp+0B8h+var_80], rdi
0x18000e4ba  test    rdi, rdi
0x18000e4bd  jz      short loc_18000E4F7
0x18000e4bf  movups  xmm6, xmmword ptr [rbx+0Ch]
0x18000e4c3  mov     rbx, [rbx+20h]
0x18000e4c7  mov     rcx, [rbx]
0x18000e4ca  mov     rax, [rcx]
0x18000e4cd  mov     rax, [rax+8]
0x18000e4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4d6  movsxd  rcx, esi
0x18000e4d9  mov     rax, [rbx]
0x18000e4dc  mov     [r15+rcx*8], rax
0x18000e4e0  add     rcx, rcx
0x18000e4e3  mov     rax, [rsp+0B8h+var_90]
0x18000e4e8  movups  xmmword ptr [rax+rcx*8], xmm6
0x18000e4ec  inc     esi
0x18000e4ee  mov     [rsp+0B8h+var_98], esi
0x18000e4f2  jmp     loc_18000E470
0x18000e4f7  jmp     short loc_18000E4A0
0x18000e4f9  xor     edx, edx
0x18000e4fb  mov     [rsp+0B8h+var_88], edx
0x18000e4ff  cmp     edx, [r12+8]
0x18000e504  jnb     short loc_18000E487
0x18000e506  mov     rax, [r12]
0x18000e50a  mov     rbx, [rax+rdx*8]
0x18000e50e  mov     [rsp+0B8h+var_70], rbx
0x18000e513  test    rbx, rbx
0x18000e516  jnz     loc_18000E487
0x18000e51c  inc     edx
0x18000e51e  jmp     short loc_18000E4FB
0x18000e520  mov     ebx, 8007000Eh
0x18000e525  jmp     short loc_18000E563
0x18000e527  mov     ebx, 8007000Eh
0x18000e52c  jmp     short loc_18000E563
0x18000e52e  mov     rbx, r14
0x18000e531  lea     rax, ds:0[r14*8]
0x18000e539  mov     [rsp+0B8h+var_68], rax
0x18000e53e  mov     ecx, 0FFFFFFFFh
0x18000e543  cmp     rax, rcx
0x18000e546  ja      loc_18000E391
0x18000e54c  shl     rbx, 4
0x18000e550  mov     [rsp+0B8h+var_60], rbx
0x18000e555  cmp     rbx, rcx
0x18000e558  ja      loc_18000E391
0x18000e55e  jmp     loc_18000E42D
0x18000e563  test    edi, edi
0x18000e565  jnz     short loc_18000E5BB
0x18000e567  test    r15, r15
0x18000e56a  jz      short loc_18000E575
0x18000e56c  mov     rcx, r15; pv
0x18000e56f  call    cs:__imp_CoTaskMemFree
0x18000e575  test    rsi, rsi
0x18000e578  jz      short loc_18000E583
0x18000e57a  mov     rcx, rsi; pv
0x18000e57d  call    cs:__imp_CoTaskMemFree
0x18000e583  test    ebx, ebx
0x18000e585  js      short loc_18000E59F
0x18000e587  movaps  xmm6, [rsp+0B8h+var_48]
0x18000e58c  add     rsp, 80h
0x18000e593  pop     r15
0x18000e595  pop     r14
0x18000e597  pop     r13
0x18000e599  pop     r12
0x18000e59b  pop     rdi
0x18000e59c  pop     rsi
0x18000e59d  pop     rbx
0x18000e59e  retn
0x18000e59f  mov     r8d, 14h; unsigned __int16
0x18000e5a5  mov     r9d, ebx; int
0x18000e5a8  mov     edx, 11Bh; unsigned int
0x18000e5ad  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18000e5b4  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000e5b9  jmp     short loc_18000E587
0x18000e5bb  mov     rcx, [rsp+0B8h+arg_18]; this
0x18000e5c3  call    ?UnlockRead@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::UnlockRead(void)
0x18000e5c8  jmp     short loc_18000E567
0x180043af0  push    rbp
0x180043af2  sub     rsp, 20h
0x180043af6  mov     rbp, rdx
0x180043af9  cmp     dword ptr [rbp+24h], 0
0x180043afd  jz      short loc_180043B10
0x180043aff  mov     rcx, [rbp+0C0h]
0x180043b06  add     rcx, 28h ; '('; this
0x180043b0a  call    ?UnlockRead@UTSemReadWriteES@@QEAAXXZ; UTSemReadWriteES::UnlockRead(void)
0x180043b0f  nop
0x180043b10  mov     rcx, [rbp+40h]; pv
0x180043b14  test    rcx, rcx
0x180043b17  jz      short loc_180043B20
0x180043b19  call    cs:__imp_CoTaskMemFree
0x180043b1f  nop
0x180043b20  mov     rcx, [rbp+28h]; pv
0x180043b24  test    rcx, rcx
0x180043b27  jz      short loc_180043B30
0x180043b29  call    cs:__imp_CoTaskMemFree
0x180043b2f  nop
0x180043b30  add     rsp, 20h
0x180043b34  pop     rbp
0x180043b35  retn
```
