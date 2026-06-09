# VGetStackTraceCore(_CONTEXT const *,VstackBuffer512 &,int)

- ea: `0x1800fe0c0`
- end: `0x1800fe4af`
- name: `?VGetStackTraceCore@@YAXPEBU_CONTEXT@@AEAVVstackBuffer512@@H@Z`
- size: `1007`
- prototype: `void(const struct _CONTEXT *, struct VstackBuffer512 *, int)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800fe4b0`

## callees

- `0x1800029ec`
- `0x1800b6680`
- `0x1800fd2a4`
- `0x1800fd608`
- `0x1800fd6dc`
- `0x1800fdd00`
- `0x1800fe0c0`
- `0x1801503e0`
- `0x18015170e`
- `0x18015197d`

## import_xrefs

- `KERNEL32!ReleaseMutex` at `0x1800fe1b4`
- `KERNEL32!ReleaseMutex` at `0x1800fe46f`
- `KERNEL32!ReleaseMutex` at `0x1800fe1b4`
- `KERNEL32!ReleaseMutex` at `0x1800fe46f`
- `KERNEL32!lstrlenA` at `0x1800fe446`
- `KERNEL32!lstrlenA` at `0x1800fe446`
- `KERNEL32!GetCurrentProcess` at `0x1800fe1ce`
- `KERNEL32!GetCurrentProcess` at `0x1800fe1ce`
- `KERNEL32!GetCurrentThread` at `0x1800fe1d7`
- `KERNEL32!GetCurrentThread` at `0x1800fe1d7`
- `KERNEL32!LeaveCriticalSection` at `0x1800fe1c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800fe47e`
- `KERNEL32!LeaveCriticalSection` at `0x1800fe1c3`
- `KERNEL32!LeaveCriticalSection` at `0x1800fe47e`
- `dbghelp!SymFunctionTableAccess64` at `0x1800fe33d`
- `dbghelp!StackWalk64` at `0x1800fe371`
- `dbghelp!StackWalk64` at `0x1800fe371`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VGetStackTraceCore(const struct _CONTEXT *a1, struct VstackBuffer512 *a2, int a3)
{
  char v6; // cl
  HANDLE v7; // r14
  const char *v8; // rdi
  char v9; // al
  unsigned int v10; // edi
  HANDLE CurrentProcess; // r13
  signed int v12; // r14d
  unsigned int v13; // edx
  unsigned int v14; // ecx
  const CHAR *v15; // rdi
  _OWORD *v16; // rax
  __int64 v17; // rcx
  int v18; // eax
  DWORD64 Offset; // r15
  int v20; // eax
  char *v21; // rdi
  int v22; // r14d
  int v23; // eax
  char *v24; // rdi
  int v25; // r14d
  int v26; // eax
  char *v27; // rdi
  int v28; // r14d
  int v29; // edi
  unsigned int v30; // eax
  char v31[4]; // [rsp+50h] [rbp-658h] BYREF
  int v32; // [rsp+54h] [rbp-654h]
  char *v33; // [rsp+58h] [rbp-650h]
  unsigned int v34; // [rsp+60h] [rbp-648h]
  const char *v35; // [rsp+68h] [rbp-640h]
  HANDLE hThread; // [rsp+70h] [rbp-638h]
  LPCSTR lpString; // [rsp+78h] [rbp-630h]
  struct VstackBuffer512 *v38; // [rsp+80h] [rbp-628h]
  __int64 v39; // [rsp+88h] [rbp-620h]
  struct _tagSTACKFRAME64 StackFrame; // [rsp+90h] [rbp-618h] BYREF
  _BYTE ContextRecord[152]; // [rsp+1A0h] [rbp-508h] BYREF
  DWORD64 v42; // [rsp+238h] [rbp-470h]
  DWORD64 v43; // [rsp+240h] [rbp-468h]
  DWORD64 v44; // [rsp+298h] [rbp-410h]

  v39 = -2;
  v38 = a2;
  v34 = *((_DWORD *)a2 + 131);
  try
  {
    sub_1800FD2A4(v31);
    v6 = 1;
    v7 = hMutex;
    if ( hMutex )
      v6 = v31[0];
    if ( v6 )
    {
      CurrentProcess = GetCurrentProcess();
      hThread = GetCurrentThread();
      v12 = 2048;
      v32 = 2048;
      sub_1800029EC(a2, "\n", 1);
      v13 = *((_DWORD *)a2 + 131) + 2048;
      v14 = *((_DWORD *)a2 + 132);
      if ( v13 > v14 )
        VstackBuffer512::reallocate(a2, v13 - v14);
      *(_BYTE *)(*((unsigned int *)a2 + 131) + *(_QWORD *)a2) = 0;
      v15 = (const CHAR *)(*(_QWORD *)a2 + *((unsigned int *)a2 + 131));
      v33 = (char *)v15;
      lpString = v15;
      v16 = ContextRecord;
      v17 = 9;
      do
      {
        *v16 = *(_OWORD *)&a1->P1Home;
        v16[1] = *(_OWORD *)&a1->P3Home;
        v16[2] = *(_OWORD *)&a1->P5Home;
        v16[3] = *(_OWORD *)&a1->ContextFlags;
        v16[4] = *(_OWORD *)&a1->SegGs;
        v16[5] = *(_OWORD *)&a1->Dr1;
        v16[6] = *(_OWORD *)&a1->Dr3;
        v16 += 8;
        *(v16 - 1) = *(_OWORD *)&a1->Dr7;
        a1 = (const struct _CONTEXT *)((char *)a1 + 128);
        --v17;
      }
      while ( v17 );
      *v16 = *(_OWORD *)&a1->P1Home;
      v16[1] = *(_OWORD *)&a1->P3Home;
      v16[2] = *(_OWORD *)&a1->P5Home;
      v16[3] = *(_OWORD *)&a1->ContextFlags;
      v16[4] = *(_OWORD *)&a1->SegGs;
      memset(&StackFrame, 0, sizeof(StackFrame));
      StackFrame.AddrPC.Offset = v44;
      StackFrame.AddrPC.Mode = AddrModeFlat;
      StackFrame.AddrStack.Offset = v42;
      StackFrame.AddrStack.Mode = AddrModeFlat;
      StackFrame.AddrFrame.Offset = v43;
      StackFrame.AddrFrame.Mode = AddrModeFlat;
      while ( StackWalk64(
                0x8664u,
                CurrentProcess,
                hThread,
                &StackFrame,
                ContextRecord,
                0,
                SymFunctionTableAccess64,
                (PGET_MODULE_BASE_ROUTINE64)GetModuleBaseRoutine,
                0) )
      {
        v18 = a3--;
        if ( v18 <= 0 )
        {
          Offset = StackFrame.AddrPC.Offset;
          v20 = sub_1800FDD00(StackFrame.AddrPC.Offset, CurrentProcess, v15, v12);
          if ( !v20 )
            break;
          v21 = (char *)&v15[v20];
          v33 = v21;
          v22 = v12 - v20;
          v32 = v22;
          if ( v22 <= 0 )
            break;
          v23 = sub_1800FD608(Offset, CurrentProcess, v21);
          v24 = &v21[v23];
          v33 = v24;
          v25 = v22 - v23;
          v32 = v25;
          if ( v25 <= 0 )
            break;
          v26 = sub_1800FD6DC(Offset, CurrentProcess, v24);
          v27 = &v24[v26];
          v33 = v27;
          v28 = v25 - v26;
          v32 = v28;
          if ( v28 <= 0 )
            break;
          *v27 = 10;
          v15 = v27 + 1;
          v33 = (char *)v15;
          *v15 = 0;
          v12 = v28 - 1;
          v32 = v12;
          if ( v12 <= 0 )
            break;
        }
      }
      v29 = *((_DWORD *)a2 + 131);
      v30 = v29 + lstrlenA(lpString);
      if ( v30 <= *((_DWORD *)a2 + 132) )
        *((_DWORD *)a2 + 131) = v30;
      if ( hMutex )
      {
        if ( v31[0] )
          ReleaseMutex(hMutex);
      }
      else
      {
        LeaveCriticalSection(&stru_1802AF4B0);
      }
    }
    else
    {
      v8 = "\n(unavailable due to resource contention)";
      v35 = "\n(unavailable due to resource contention)";
      do
      {
        v9 = *v8++;
        v35 = v8;
      }
      while ( v9 );
      v10 = (_DWORD)v8 - (unsigned int)"\n(unavailable due to resource contention)" - 1;
      if ( v10 + *((_DWORD *)a2 + 131) > *((_DWORD *)a2 + 132) )
      {
        VstackBuffer512::reallocate(a2, v10);
        v7 = hMutex;
      }
      memcpy((void *)(*(_QWORD *)a2 + *((unsigned int *)a2 + 131)), "\n(unavailable due to resource contention)", v10);
      *((_DWORD *)a2 + 131) += v10;
      *(_BYTE *)(*((unsigned int *)a2 + 131) + *(_QWORD *)a2) = 0;
      if ( v7 )
      {
        if ( v31[0] )
          ReleaseMutex(v7);
      }
      else
      {
        LeaveCriticalSection(&stru_1802AF4B0);
      }
    }
  }
  catch ( ... )
  {
    if ( v34 <= *((_DWORD *)v38 + 132) )
      *((_DWORD *)v38 + 131) = v34;
  }
}

```

## disassembly

```asm
0x1800fe0c0  mov     rax, rsp
0x1800fe0c3  push    rdi
0x1800fe0c4  push    r12
0x1800fe0c6  push    r13
0x1800fe0c8  push    r14
0x1800fe0ca  push    r15
0x1800fe0cc  sub     rsp, 680h
0x1800fe0d3  mov     qword ptr [rax-620h], 0FFFFFFFFFFFFFFFEh
0x1800fe0de  mov     [rax+20h], rsi
0x1800fe0e2  mov     rax, cs:__security_cookie
0x1800fe0e9  xor     rax, rsp
0x1800fe0ec  mov     [rsp+6A8h+var_38], rax
0x1800fe0f4  mov     r12d, r8d
0x1800fe0f7  mov     rsi, rdx
0x1800fe0fa  mov     r15, rcx
0x1800fe0fd  mov     [rsp+6A8h+var_628], rdx
0x1800fe105  mov     eax, [rdx+20Ch]
0x1800fe10b  mov     [rsp+6A8h+var_648], eax
0x1800fe10f  lea     rcx, [rsp+6A8h+var_658]
0x1800fe114  call    sub_1800FD2A4
0x1800fe119  nop
0x1800fe11a  mov     ecx, 1
0x1800fe11f  movzx   eax, [rsp+6A8h+var_658]
0x1800fe124  mov     r14, cs:hMutex
0x1800fe12b  test    r14, r14
0x1800fe12e  cmovnz  ecx, eax
0x1800fe131  test    cl, cl
0x1800fe133  jnz     loc_1800FE1CE
0x1800fe139  lea     r15, aUnavailableDue; "\n(unavailable due to resource contenti"...
0x1800fe140  mov     rdi, r15
0x1800fe143  mov     [rsp+6A8h+var_640], r15
0x1800fe148  mov     al, [rdi]
0x1800fe14a  inc     rdi
0x1800fe14d  mov     [rsp+6A8h+var_640], rdi
0x1800fe152  test    al, al
0x1800fe154  jz      short loc_1800FE158
0x1800fe156  jmp     short loc_1800FE148
0x1800fe158  sub     edi, r15d
0x1800fe15b  dec     edi
0x1800fe15d  mov     ecx, [rsi+20Ch]
0x1800fe163  add     ecx, edi
0x1800fe165  cmp     ecx, [rsi+210h]
0x1800fe16b  jbe     short loc_1800FE17E
0x1800fe16d  mov     edx, edi; unsigned int
0x1800fe16f  mov     rcx, rsi; this
0x1800fe172  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x1800fe177  mov     r14, cs:hMutex
0x1800fe17e  mov     r8d, edi; Size
0x1800fe181  mov     ecx, [rsi+20Ch]
0x1800fe187  add     rcx, [rsi]; void *
0x1800fe18a  mov     rdx, r15; Src
0x1800fe18d  call    memcpy
0x1800fe192  add     [rsi+20Ch], edi
0x1800fe198  mov     edx, [rsi+20Ch]
0x1800fe19e  mov     rax, [rsi]
0x1800fe1a1  mov     byte ptr [rdx+rax], 0
0x1800fe1a5  test    r14, r14
0x1800fe1a8  jz      short loc_1800FE1BC
0x1800fe1aa  cmp     [rsp+6A8h+var_658], 0
0x1800fe1af  jz      short loc_1800FE1C9
0x1800fe1b1  mov     rcx, r14; hMutex
0x1800fe1b4  call    cs:ReleaseMutex
0x1800fe1ba  jmp     short loc_1800FE1C9
0x1800fe1bc  lea     rcx, stru_1802AF4B0; lpCriticalSection
0x1800fe1c3  call    cs:LeaveCriticalSection
0x1800fe1c9  jmp     loc_1800FE485
0x1800fe1ce  call    cs:GetCurrentProcess
0x1800fe1d4  mov     r13, rax
0x1800fe1d7  call    cs:GetCurrentThread
0x1800fe1dd  mov     [rsp+6A8h+hThread], rax
0x1800fe1e2  mov     r14d, 800h
0x1800fe1e8  mov     [rsp+6A8h+var_654], r14d
0x1800fe1ed  mov     r8d, 1
0x1800fe1f3  lea     rdx, asc_1801821E8; "\n"
0x1800fe1fa  mov     rcx, rsi
0x1800fe1fd  call    sub_1800029EC
0x1800fe202  mov     edx, [rsi+20Ch]
0x1800fe208  add     edx, r14d
0x1800fe20b  mov     ecx, [rsi+210h]
0x1800fe211  cmp     edx, ecx
0x1800fe213  jbe     short loc_1800FE21F
0x1800fe215  sub     edx, ecx; unsigned int
0x1800fe217  mov     rcx, rsi; this
0x1800fe21a  call    ?reallocate@VstackBuffer512@@AEAAXI@Z; VstackBuffer512::reallocate(uint)
0x1800fe21f  mov     ecx, [rsi+20Ch]
0x1800fe225  mov     rax, [rsi]
0x1800fe228  mov     byte ptr [rcx+rax], 0
0x1800fe22c  mov     edi, [rsi+20Ch]
0x1800fe232  add     rdi, [rsi]
0x1800fe235  mov     [rsp+6A8h+var_650], rdi
0x1800fe23a  mov     [rsp+6A8h+lpString], rdi
0x1800fe23f  lea     rax, [rsp+6A8h+var_508]
0x1800fe247  mov     ecx, 9
0x1800fe24c  lea     edx, [rcx+77h]
0x1800fe24f  movups  xmm0, xmmword ptr [r15]
0x1800fe253  movups  xmmword ptr [rax], xmm0
0x1800fe256  movups  xmm1, xmmword ptr [r15+10h]
0x1800fe25b  movups  xmmword ptr [rax+10h], xmm1
0x1800fe25f  movups  xmm0, xmmword ptr [r15+20h]
0x1800fe264  movups  xmmword ptr [rax+20h], xmm0
0x1800fe268  movups  xmm1, xmmword ptr [r15+30h]
0x1800fe26d  movups  xmmword ptr [rax+30h], xmm1
0x1800fe271  movups  xmm0, xmmword ptr [r15+40h]
0x1800fe276  movups  xmmword ptr [rax+40h], xmm0
0x1800fe27a  movups  xmm1, xmmword ptr [r15+50h]
0x1800fe27f  movups  xmmword ptr [rax+50h], xmm1
0x1800fe283  movups  xmm0, xmmword ptr [r15+60h]
0x1800fe288  movups  xmmword ptr [rax+60h], xmm0
0x1800fe28c  add     rax, rdx
0x1800fe28f  movups  xmm1, xmmword ptr [r15+70h]
0x1800fe294  movups  xmmword ptr [rax-10h], xmm1
0x1800fe298  add     r15, rdx
0x1800fe29b  sub     rcx, 1
0x1800fe29f  jnz     short loc_1800FE24F
0x1800fe2a1  movups  xmm0, xmmword ptr [r15]
0x1800fe2a5  movups  xmmword ptr [rax], xmm0
0x1800fe2a8  movups  xmm1, xmmword ptr [r15+10h]
0x1800fe2ad  movups  xmmword ptr [rax+10h], xmm1
0x1800fe2b1  movups  xmm0, xmmword ptr [r15+20h]
0x1800fe2b6  movups  xmmword ptr [rax+20h], xmm0
0x1800fe2ba  movups  xmm1, xmmword ptr [r15+30h]
0x1800fe2bf  movups  xmmword ptr [rax+30h], xmm1
0x1800fe2c3  movups  xmm0, xmmword ptr [r15+40h]
0x1800fe2c8  movups  xmmword ptr [rax+40h], xmm0
0x1800fe2cc  xor     edx, edx; Val
0x1800fe2ce  mov     r8d, 108h; Size
0x1800fe2d4  lea     rcx, [rsp+6A8h+StackFrame]; void *
0x1800fe2dc  call    memset
0x1800fe2e1  mov     rax, [rsp+6A8h+var_410]
0x1800fe2e9  mov     [rsp+6A8h+StackFrame.AddrPC.Offset], rax
0x1800fe2f1  mov     ecx, 3
0x1800fe2f6  mov     [rsp+6A8h+StackFrame.AddrPC.Mode], ecx
0x1800fe2fd  mov     rax, [rsp+6A8h+var_470]
0x1800fe305  mov     [rsp+6A8h+StackFrame.AddrStack.Offset], rax
0x1800fe30d  mov     [rsp+6A8h+StackFrame.AddrStack.Mode], ecx
0x1800fe314  mov     rax, [rsp+6A8h+var_468]
0x1800fe31c  mov     [rsp+6A8h+StackFrame.AddrFrame.Offset], rax
0x1800fe324  mov     [rsp+6A8h+StackFrame.AddrFrame.Mode], ecx
0x1800fe32b  and     [rsp+6A8h+var_668], 0
0x1800fe331  lea     rax, GetModuleBaseRoutine
0x1800fe338  mov     [rsp+6A8h+GetModuleBaseRoutine], rax; GetModuleBaseRoutine
0x1800fe33d  mov     rax, cs:SymFunctionTableAccess64
0x1800fe344  mov     [rsp+6A8h+FunctionTableAccessRoutine], rax; FunctionTableAccessRoutine
0x1800fe349  and     [rsp+6A8h+var_680], 0
0x1800fe34f  lea     rax, [rsp+6A8h+var_508]
0x1800fe357  mov     [rsp+6A8h+ContextRecord], rax; ContextRecord
0x1800fe35c  lea     r9, [rsp+6A8h+StackFrame]; StackFrame
0x1800fe364  mov     r8, [rsp+6A8h+hThread]; hThread
0x1800fe369  mov     rdx, r13; hProcess
0x1800fe36c  mov     ecx, 8664h; MachineType
0x1800fe371  call    cs:StackWalk64
0x1800fe377  test    eax, eax
0x1800fe379  jz      loc_1800FE43B
0x1800fe37f  mov     eax, r12d
0x1800fe382  dec     r12d
0x1800fe385  mov     [rsp+6A8h+arg_10], r12d
0x1800fe38d  test    eax, eax
0x1800fe38f  jg      short loc_1800FE32B
0x1800fe391  mov     r15, [rsp+6A8h+StackFrame.AddrPC.Offset]
0x1800fe399  mov     r9d, r14d; nSize
0x1800fe39c  mov     r8, rdi; ImageName
0x1800fe39f  mov     rdx, r13; hProcess
0x1800fe3a2  mov     rcx, r15; Address
0x1800fe3a5  call    sub_1800FDD00
0x1800fe3aa  test    eax, eax
0x1800fe3ac  jz      loc_1800FE43B
0x1800fe3b2  movsxd  rcx, eax
0x1800fe3b5  add     rdi, rcx
0x1800fe3b8  mov     [rsp+6A8h+var_650], rdi
0x1800fe3bd  sub     r14d, eax
0x1800fe3c0  mov     [rsp+6A8h+var_654], r14d
0x1800fe3c5  test    r14d, r14d
0x1800fe3c8  jle     short loc_1800FE43B
0x1800fe3ca  mov     r9d, r14d
0x1800fe3cd  mov     r8, rdi; Buffer
0x1800fe3d0  mov     rdx, r13; hProcess
0x1800fe3d3  mov     rcx, r15; Address
0x1800fe3d6  call    sub_1800FD608
0x1800fe3db  movsxd  rdx, eax
0x1800fe3de  add     rdi, rdx
0x1800fe3e1  mov     [rsp+6A8h+var_650], rdi
0x1800fe3e6  sub     r14d, eax
0x1800fe3e9  mov     [rsp+6A8h+var_654], r14d
0x1800fe3ee  test    r14d, r14d
0x1800fe3f1  jle     short loc_1800FE43B
0x1800fe3f3  mov     r9d, r14d
0x1800fe3f6  mov     r8, rdi; Buffer
0x1800fe3f9  mov     rdx, r13; hProcess
0x1800fe3fc  mov     rcx, r15; qwAddr
0x1800fe3ff  call    sub_1800FD6DC
0x1800fe404  movsxd  rcx, eax
0x1800fe407  add     rdi, rcx
0x1800fe40a  mov     [rsp+6A8h+var_650], rdi
0x1800fe40f  sub     r14d, eax
0x1800fe412  mov     [rsp+6A8h+var_654], r14d
0x1800fe417  test    r14d, r14d
0x1800fe41a  jle     short loc_1800FE43B
0x1800fe41c  mov     byte ptr [rdi], 0Ah
0x1800fe41f  inc     rdi
0x1800fe422  mov     [rsp+6A8h+var_650], rdi
0x1800fe427  mov     byte ptr [rdi], 0
0x1800fe42a  dec     r14d
0x1800fe42d  mov     [rsp+6A8h+var_654], r14d
0x1800fe432  test    r14d, r14d
0x1800fe435  jg      loc_1800FE32B
0x1800fe43b  mov     edi, [rsi+20Ch]
0x1800fe441  mov     rcx, [rsp+6A8h+lpString]; lpString
0x1800fe446  call    cs:lstrlenA
0x1800fe44c  add     eax, edi
0x1800fe44e  cmp     eax, [rsi+210h]
0x1800fe454  ja      short loc_1800FE45C
0x1800fe456  mov     [rsi+20Ch], eax
0x1800fe45c  mov     rcx, cs:hMutex; hMutex
0x1800fe463  test    rcx, rcx
0x1800fe466  jz      short loc_1800FE477
0x1800fe468  cmp     [rsp+6A8h+var_658], 0
0x1800fe46d  jz      short loc_1800FE485
0x1800fe46f  call    cs:ReleaseMutex
0x1800fe475  jmp     short loc_1800FE485
0x1800fe477  lea     rcx, stru_1802AF4B0; lpCriticalSection
0x1800fe47e  call    cs:LeaveCriticalSection
0x1800fe484  nop
0x1800fe485  mov     rcx, [rsp+6A8h+var_38]
0x1800fe48d  xor     rcx, rsp
0x1800fe490  call    sub_1801503E0
0x1800fe495  mov     rsi, [rsp+6A8h+arg_18]
0x1800fe49d  add     rsp, 680h
0x1800fe4a4  pop     r15
0x1800fe4a6  pop     r14
0x1800fe4a8  pop     r13
0x1800fe4aa  pop     r12
0x1800fe4ac  pop     rdi
0x1800fe4ad  retn
```
