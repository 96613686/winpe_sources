# sub_1800BD4EC

- ea: `0x1800bd4ec`
- end: `0x1800bd81f`
- name: `sub_1800BD4EC`
- size: `819`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1800b3180`
- `0x1800b46c0`

## callees

- `0x180004678`
- `0x180007f5c`
- `0x180008d70`
- `0x180009628`
- `0x18000b710`
- `0x180015a2c`
- `0x180018d7c`
- `0x1800955f8`
- `0x1800bd4ec`
- `0x1800f3b5c`
- `0x1800fea68`
- `0x18013b830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd560`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800bd560`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bd519`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bd53e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bd519`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleA` at `0x1800bd53e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd529`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd54e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd529`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bd54e`

## string_xrefs

- `0x1800bd522`: `SetThreadDescription`
- `0x1800bd547`: `SetThreadDescription`
- `0x1800bd512`: `Kernel32.dll`
- `0x1800bd537`: `KernelBase.dll`
- `0x1800bd669`: `setThreadName`
- `0x1800bd690`: `../../../../third_party/wp.client/msinternal/src/base/core/windows/thread-win.cpp`

## pseudocode

```c
__int64 __fastcall sub_1800BD4EC(__int64 a1, __int64 a2)
{
  HMODULE ModuleHandleA; // rax
  FARPROC ProcAddress; // rdi
  HMODULE v6; // rax
  HANDLE CurrentThread; // rax
  int v8; // edi
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  char *v12; // rcx
  _OWORD v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD v15[2]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v16[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v17; // [rsp+A8h] [rbp-58h]
  _BYTE v18[40]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v19[72]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v20[64]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v21[16]; // [rsp+160h] [rbp+60h] BYREF
  char v22; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v23[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v24[40]; // [rsp+1B8h] [rbp+B8h] BYREF
  char v25; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v26[40]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v27[32]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v28[40]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE *v29; // [rsp+290h] [rbp+190h] BYREF
  int v30; // [rsp+298h] [rbp+198h] BYREF

  ModuleHandleA = GetModuleHandleA("Kernel32.dll");
  ProcAddress = GetProcAddress(ModuleHandleA, "SetThreadDescription");
  if ( (ProcAddress
     || (v6 = GetModuleHandleA("KernelBase.dll"), (ProcAddress = GetProcAddress(v6, "SetThreadDescription")) != 0))
    && (CurrentThread = GetCurrentThread(),
        v8 = ((__int64 (__fastcall *)(HANDLE, __int64))ProcAddress)(CurrentThread, a2),
        v8 < 0) )
  {
    _mm_lfence();
    v17 = v19;
    *(_QWORD *)&v14[0] = a2;
    *((_QWORD *)&v14[0] + 1) = sub_1800FEA68(a2);
    v9 = sub_1800955F8(v21, v14);
    memset(v15, 0, sizeof(v15));
    if ( *(_BYTE *)(v9 + 120) )
    {
      v10 = *(_QWORD *)(v9 + 16);
      if ( *(_QWORD *)(v9 + 24) > 0xFu )
        v9 = *(_QWORD *)v9;
      sub_180009628(v15, v9, v10);
    }
    else
    {
      sub_180004678(v15, &qword_180149390, 0);
    }
    sub_180008D70(v20, "Name", v15);
    v30 = 0;
    sub_18000B710(v19, &v30, &v29);
    sub_180015A2C(v19, v14, v20);
    v29 = v18;
    v18[32] = 0;
    memset(v14, 0, sizeof(v14));
    sub_180004678(v14, "setThreadName", 13);
    memset(v16, 0, sizeof(v16));
    sub_180004678(v16, "../../../../third_party/wp.client/msinternal/src/base/core/windows/thread-win.cpp", 81);
    v11 = sub_180018D7C((unsigned int)&v25, v8, (unsigned int)v16, 43, (__int64)v14, 0, (__int64)v18, (__int64)v19);
    *(_OWORD *)a1 = *(_OWORD *)v11;
    *(_OWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    *(_QWORD *)(a1 + 40) = 0;
    *(_OWORD *)(a1 + 16) = *(_OWORD *)(v11 + 16);
    *(_OWORD *)(a1 + 32) = *(_OWORD *)(v11 + 32);
    *(_QWORD *)(v11 + 32) = 0;
    *(_QWORD *)(v11 + 40) = 15;
    *(_BYTE *)(v11 + 16) = 0;
    *(_DWORD *)(a1 + 48) = *(_DWORD *)(v11 + 48);
    *(_OWORD *)(a1 + 56) = 0;
    *(_QWORD *)(a1 + 72) = 0;
    *(_QWORD *)(a1 + 80) = 0;
    *(_OWORD *)(a1 + 56) = *(_OWORD *)(v11 + 56);
    *(_OWORD *)(a1 + 72) = *(_OWORD *)(v11 + 72);
    *(_QWORD *)(v11 + 72) = 0;
    *(_QWORD *)(v11 + 80) = 15;
    *(_BYTE *)(v11 + 56) = 0;
    *(_OWORD *)(a1 + 88) = 0;
    *(_QWORD *)(a1 + 104) = 0;
    *(_QWORD *)(a1 + 112) = 0;
    *(_OWORD *)(a1 + 88) = *(_OWORD *)(v11 + 88);
    *(_OWORD *)(a1 + 104) = *(_OWORD *)(v11 + 104);
    *(_QWORD *)(v11 + 104) = 0;
    *(_QWORD *)(v11 + 112) = 15;
    *(_BYTE *)(v11 + 88) = 0;
    *(_BYTE *)(a1 + 120) = 0;
    sub_180007F5C(v28);
    sub_180007F5C(v27);
    sub_180007F5C(v26);
    sub_180007F5C(v16);
    sub_180007F5C(v14);
    sub_1800F3B5C(v20, 64, 1, sub_18000D430);
    sub_180007F5C(v15);
    if ( v24[32] )
    {
      v12 = v21;
    }
    else
    {
      sub_180007F5C(v24);
      sub_180007F5C(v23);
      v12 = &v22;
    }
    sub_180007F5C(v12);
  }
  else
  {
    *(_BYTE *)(a1 + 120) = 1;
  }
  return a1;
}

```

## disassembly

```asm
0x1800bd4ec  mov     [rsp-8+arg_0], rbx
0x1800bd4f1  mov     [rsp-8+arg_8], rsi
0x1800bd4f6  push    rbp
0x1800bd4f7  push    rdi
0x1800bd4f8  push    r14
0x1800bd4fa  lea     rbp, [rsp-160h]
0x1800bd502  sub     rsp, 260h
0x1800bd509  mov     rsi, rdx
0x1800bd50c  mov     rbx, rcx
0x1800bd50f  xor     r14d, r14d
0x1800bd512  lea     rcx, aKernel32Dll_0; "Kernel32.dll"
0x1800bd519  call    cs:GetModuleHandleA
0x1800bd51f  mov     rcx, rax; hModule
0x1800bd522  lea     rdx, aSetthreaddescr; "SetThreadDescription"
0x1800bd529  call    cs:__imp_GetProcAddress
0x1800bd52f  mov     rdi, rax
0x1800bd532  test    rax, rax
0x1800bd535  jnz     short loc_1800BD560
0x1800bd537  lea     rcx, aKernelbaseDll_1; "KernelBase.dll"
0x1800bd53e  call    cs:GetModuleHandleA
0x1800bd544  mov     rcx, rax; hModule
0x1800bd547  lea     rdx, aSetthreaddescr; "SetThreadDescription"
0x1800bd54e  call    cs:__imp_GetProcAddress
0x1800bd554  mov     rdi, rax
0x1800bd557  test    rax, rax
0x1800bd55a  jz      loc_1800BD800
0x1800bd560  call    cs:GetCurrentThread
0x1800bd566  mov     rcx, rax
0x1800bd569  mov     rdx, rsi
0x1800bd56c  mov     rax, rdi
0x1800bd56f  call    cs:__guard_dispatch_icall_fptr
0x1800bd575  mov     edi, eax
0x1800bd577  test    eax, eax
0x1800bd579  jns     loc_1800BD800
0x1800bd57f  lfence
0x1800bd582  lea     rax, [rbp+170h+var_198]
0x1800bd586  mov     [rbp+170h+var_1C8], rax
0x1800bd58a  mov     rcx, rsi
0x1800bd58d  call    sub_1800FEA68
0x1800bd592  mov     qword ptr [rsp+270h+var_230], rsi
0x1800bd597  mov     qword ptr [rsp+270h+var_230+8], rax
0x1800bd59c  lea     rdx, [rsp+270h+var_230]
0x1800bd5a1  lea     rcx, [rbp+170h+var_110]
0x1800bd5a5  call    sub_1800955F8
0x1800bd5aa  nop
0x1800bd5ab  mov     esi, 0Fh
0x1800bd5b0  xorps   xmm0, xmm0
0x1800bd5b3  xorps   xmm1, xmm1
0x1800bd5b6  movups  [rsp+270h+var_208], xmm0
0x1800bd5bb  movdqu  [rsp+270h+var_1F8], xmm1
0x1800bd5c1  cmp     [rax+78h], r14b
0x1800bd5c5  jz      short loc_1800BD5E3
0x1800bd5c7  mov     r8, [rax+10h]
0x1800bd5cb  cmp     [rax+18h], rsi
0x1800bd5cf  jbe     short loc_1800BD5D4
0x1800bd5d1  mov     rax, [rax]
0x1800bd5d4  mov     rdx, rax
0x1800bd5d7  lea     rcx, [rsp+270h+var_208]
0x1800bd5dc  call    sub_180009628
0x1800bd5e1  jmp     short loc_1800BD5F8
0x1800bd5e3  xor     r8d, r8d
0x1800bd5e6  lea     rdx, qword_180149390
0x1800bd5ed  lea     rcx, [rsp+270h+var_208]
0x1800bd5f2  call    sub_180004678
0x1800bd5f7  nop
0x1800bd5f8  lea     r8, [rsp+270h+var_208]
0x1800bd5fd  lea     rdx, aName_1; "Name"
0x1800bd604  lea     rcx, [rbp+170h+var_150]
0x1800bd608  call    sub_180008D70
0x1800bd60d  nop
0x1800bd60e  mov     [rbp+170h+arg_18], 0
0x1800bd618  lea     r8, [rbp+170h+arg_10]
0x1800bd61f  lea     rdx, [rbp+170h+arg_18]
0x1800bd626  lea     rcx, [rbp+170h+var_198]
0x1800bd62a  call    sub_18000B710
0x1800bd62f  nop
0x1800bd630  lea     r8, [rbp+170h+var_150]
0x1800bd634  lea     rdx, [rsp+270h+var_230]
0x1800bd639  lea     rcx, [rbp+170h+var_198]
0x1800bd63d  call    sub_180015A2C
0x1800bd642  nop
0x1800bd643  lea     rax, [rbp+170h+var_1C0]
0x1800bd647  mov     [rbp+170h+arg_10], rax
0x1800bd64e  mov     [rbp+170h+var_1A0], r14b
0x1800bd652  xorps   xmm0, xmm0
0x1800bd655  movups  [rsp+270h+var_230], xmm0
0x1800bd65a  xorps   xmm1, xmm1
0x1800bd65d  movdqu  [rsp+270h+var_220], xmm1
0x1800bd663  mov     r8d, 0Dh
0x1800bd669  lea     rdx, aSetthreadname; "setThreadName"
0x1800bd670  lea     rcx, [rsp+270h+var_230]
0x1800bd675  call    sub_180004678
0x1800bd67a  nop
0x1800bd67b  xorps   xmm0, xmm0
0x1800bd67e  movups  [rbp+170h+var_1E8], xmm0
0x1800bd682  xorps   xmm1, xmm1
0x1800bd685  movdqu  [rbp+170h+var_1D8], xmm1
0x1800bd68a  mov     r8d, 51h ; 'Q'
0x1800bd690  lea     rdx, aThirdPartyWpCl_34; "../../../../third_party/wp.client/msint"...
0x1800bd697  lea     rcx, [rbp+170h+var_1E8]
0x1800bd69b  call    sub_180004678
0x1800bd6a0  nop
0x1800bd6a1  lea     rax, [rbp+170h+var_198]
0x1800bd6a5  mov     [rsp+270h+var_238], rax
0x1800bd6aa  lea     rax, [rbp+170h+var_1C0]
0x1800bd6ae  mov     [rsp+270h+var_240], rax
0x1800bd6b3  mov     [rsp+270h+var_248], r14
0x1800bd6b8  lea     rax, [rsp+270h+var_230]
0x1800bd6bd  mov     [rsp+270h+var_250], rax
0x1800bd6c2  mov     r9d, 2Bh ; '+'
0x1800bd6c8  lea     r8, [rbp+170h+var_1E8]
0x1800bd6cc  mov     edx, edi
0x1800bd6ce  lea     rcx, [rbp+170h+var_90]
0x1800bd6d5  call    sub_180018D7C
0x1800bd6da  mov     rcx, rax
0x1800bd6dd  movups  xmm0, xmmword ptr [rax]
0x1800bd6e0  movdqu  xmmword ptr [rbx], xmm0
0x1800bd6e4  xorps   xmm0, xmm0
0x1800bd6e7  movups  xmmword ptr [rbx+10h], xmm0
0x1800bd6eb  mov     [rbx+20h], r14
0x1800bd6ef  mov     [rbx+28h], r14
0x1800bd6f3  movups  xmm0, xmmword ptr [rax+10h]
0x1800bd6f7  movups  xmmword ptr [rbx+10h], xmm0
0x1800bd6fb  movups  xmm1, xmmword ptr [rax+20h]
0x1800bd6ff  movups  xmmword ptr [rbx+20h], xmm1
0x1800bd703  mov     [rax+20h], r14
0x1800bd707  mov     [rax+28h], rsi
0x1800bd70b  mov     [rax+10h], r14b
0x1800bd70f  mov     eax, [rax+30h]
0x1800bd712  mov     [rbx+30h], eax
0x1800bd715  xorps   xmm0, xmm0
0x1800bd718  movups  xmmword ptr [rbx+38h], xmm0
0x1800bd71c  mov     [rbx+48h], r14
0x1800bd720  mov     [rbx+50h], r14
0x1800bd724  movups  xmm0, xmmword ptr [rcx+38h]
0x1800bd728  movups  xmmword ptr [rbx+38h], xmm0
0x1800bd72c  movups  xmm1, xmmword ptr [rcx+48h]
0x1800bd730  movups  xmmword ptr [rbx+48h], xmm1
0x1800bd734  mov     [rcx+48h], r14
0x1800bd738  mov     [rcx+50h], rsi
0x1800bd73c  mov     [rcx+38h], r14b
0x1800bd740  xorps   xmm0, xmm0
0x1800bd743  movups  xmmword ptr [rbx+58h], xmm0
0x1800bd747  mov     [rbx+68h], r14
0x1800bd74b  mov     [rbx+70h], r14
0x1800bd74f  movups  xmm0, xmmword ptr [rcx+58h]
0x1800bd753  movups  xmmword ptr [rbx+58h], xmm0
0x1800bd757  movups  xmm1, xmmword ptr [rcx+68h]
0x1800bd75b  movups  xmmword ptr [rbx+68h], xmm1
0x1800bd75f  mov     [rcx+68h], r14
0x1800bd763  mov     [rcx+70h], rsi
0x1800bd767  mov     [rcx+58h], r14b
0x1800bd76b  mov     [rbx+78h], r14b
0x1800bd76f  lea     rcx, [rbp+170h+var_38]
0x1800bd776  call    sub_180007F5C
0x1800bd77b  lea     rcx, [rbp+170h+var_58]
0x1800bd782  call    sub_180007F5C
0x1800bd787  lea     rcx, [rbp+170h+var_80]
0x1800bd78e  call    sub_180007F5C
0x1800bd793  nop
0x1800bd794  lea     rcx, [rbp+170h+var_1E8]
0x1800bd798  call    sub_180007F5C
0x1800bd79d  nop
0x1800bd79e  lea     rcx, [rsp+270h+var_230]
0x1800bd7a3  call    sub_180007F5C
0x1800bd7a8  nop
0x1800bd7a9  lea     r9, sub_18000D430
0x1800bd7b0  mov     edx, 40h ; '@'
0x1800bd7b5  lea     r8d, [rdx-3Fh]
0x1800bd7b9  lea     rcx, [rbp+170h+var_150]
0x1800bd7bd  call    sub_1800F3B5C
0x1800bd7c2  nop
0x1800bd7c3  lea     rcx, [rsp+270h+var_208]
0x1800bd7c8  call    sub_180007F5C
0x1800bd7cd  nop
0x1800bd7ce  cmp     [rbp+170h+var_98], r14b
0x1800bd7d5  jz      short loc_1800BD7DD
0x1800bd7d7  lea     rcx, [rbp+170h+var_110]
0x1800bd7db  jmp     short loc_1800BD7F9
0x1800bd7dd  lea     rcx, [rbp+170h+var_B8]
0x1800bd7e4  call    sub_180007F5C
0x1800bd7e9  lea     rcx, [rbp+170h+var_D8]
0x1800bd7f0  call    sub_180007F5C
0x1800bd7f5  lea     rcx, [rbp+170h+var_100]
0x1800bd7f9  call    sub_180007F5C
0x1800bd7fe  jmp     short loc_1800BD804
0x1800bd800  mov     byte ptr [rbx+78h], 1
0x1800bd804  mov     rax, rbx
0x1800bd807  lea     r11, [rsp+270h+var_10]
0x1800bd80f  mov     rbx, [r11+20h]
0x1800bd813  mov     rsi, [r11+28h]
0x1800bd817  mov     rsp, r11
0x1800bd81a  pop     r14
0x1800bd81c  pop     rdi
0x1800bd81d  pop     rbp
0x1800bd81e  retn
```
