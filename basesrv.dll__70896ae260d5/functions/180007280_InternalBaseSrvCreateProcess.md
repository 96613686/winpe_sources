# InternalBaseSrvCreateProcess

- ea: `0x180007280`
- end: `0x18000745b`
- name: `InternalBaseSrvCreateProcess`
- size: `475`
- prototype: `NTSTATUS __fastcall(int, int, unsigned int, int, __int64, HANDLE ProcessHandle, __int64, unsigned int *, __int16, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180006ee0`

## callees

- `0x180007280`
- `0x18000e010`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800072dd`
- `ntdll!NtQueryInformationProcess` at `0x1800072dd`
- `ntdll!NtSetInformationProcess` at `0x180007326`
- `ntdll!NtSetInformationProcess` at `0x180007326`
- `CSRSRV!CsrCreateProcess` at `0x1800073f5`
- `CSRSRV!CsrCreateProcess` at `0x1800073f5`

## pseudocode

```c
NTSTATUS __fastcall InternalBaseSrvCreateProcess(
        int a1,
        int a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        HANDLE ProcessHandle,
        __int64 a7,
        unsigned int *a8,
        __int16 a9,
        __int64 a10,
        _DWORD *a11)
{
  HANDLE v11; // rbx
  NTSTATUS result; // eax
  __int64 v17; // rdi
  int v18; // edx
  int v19; // ecx
  __int64 v20; // r9
  unsigned int *v21; // rdi
  __int64 (__fastcall *v22)(_QWORD, _QWORD, _QWORD, __int64); // r10
  __int64 v23; // r9
  _QWORD v24[6]; // [rsp+30h] [rbp-58h] BYREF
  __int128 v25; // [rsp+60h] [rbp-28h]
  int ProcessInformation; // [rsp+90h] [rbp+8h] BYREF

  v11 = ProcessHandle;
  memset(v24, 0, sizeof(v24));
  v25 = 0;
  if ( !a1 )
    goto LABEL_26;
  v24[0] = 64;
  result = NtQueryInformationProcess(ProcessHandle, ProcessBasicInformation, v24, 0x40u, 0);
  if ( result < 0 )
    return result;
  if ( (BYTE8(v25) & 1) == 0 )
    return -1073741811;
LABEL_26:
  if ( !a4
    || (ProcessInformation = 1,
        result = NtSetInformationProcess(v11, ProcessWx86Information, &ProcessInformation, 4u),
        result >= 0) )
  {
    v17 = a5;
    if ( a1
      || (*(_DWORD *)(a5 + 92) & 0x2000) != 0
      || !sxsFunctions
      || !a10
      || (result = (*(__int64 (__fastcall **)(_QWORD, HANDLE))(sxsFunctions + 8))(*(_QWORD *)(a5 + 80), v11), result >= 0) )
    {
      v18 = (a1 != 0 ? 0x2000 : 0) | 4;
      if ( (a9 & 0x200) == 0 )
        v18 = a1 != 0 ? 0x2000 : 0;
      v19 = v18 | 0x20;
      if ( (a3 & 2) != 0 )
        v19 = v18;
      if ( a2 )
      {
        v19 |= ((a3 & 1) << 9) + 128;
        if ( (a4 & 0xE0) != 0 )
          v19 |= 0x400u;
      }
      v20 = *(_QWORD *)(v17 + 48);
      v21 = a8;
      result = CsrCreateProcess(v11, a7, a8, v20, v19, 0);
      if ( result >= 0 )
      {
        v22 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, __int64))UserNotifyProcessCreate;
        *a11 = 0;
        if ( v22 )
        {
          v23 = a3 | 0x10;
          if ( !a2 )
            v23 = a3;
          return v22(*v21, 0, 0, v23);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180007280  mov     rax, rsp
0x180007283  mov     [rax+18h], rbx
0x180007287  mov     [rax+20h], rbp
0x18000728b  push    rsi
0x18000728c  push    r14
0x18000728e  push    r15
0x180007290  sub     rsp, 70h
0x180007294  mov     rbx, [rsp+88h+ProcessHandle]
0x18000729c  xorps   xmm0, xmm0
0x18000729f  mov     ebp, r9d
0x1800072a2  mov     r14d, r8d
0x1800072a5  mov     r15d, edx
0x1800072a8  mov     esi, ecx
0x1800072aa  movups  xmmword ptr [rax-58h], xmm0
0x1800072ae  movups  xmmword ptr [rax-48h], xmm0
0x1800072b2  movups  xmmword ptr [rax-38h], xmm0
0x1800072b6  movups  xmmword ptr [rax-28h], xmm0
0x1800072ba  test    ecx, ecx
0x1800072bc  jz      short loc_180007302
0x1800072be  mov     r9d, 40h ; '@'; ProcessInformationLength
0x1800072c4  mov     qword ptr [rax-58h], 40h ; '@'
0x1800072cc  lea     r8, [rax-58h]; ProcessInformation
0x1800072d0  mov     qword ptr [rax-68h], 0
0x1800072d8  xor     edx, edx; ProcessInformationClass
0x1800072da  mov     rcx, rbx; ProcessHandle
0x1800072dd  call    cs:__imp_NtQueryInformationProcess
0x1800072e4  nop     dword ptr [rax+rax+00h]
0x1800072e9  test    eax, eax
0x1800072eb  js      loc_180007444
0x1800072f1  test    [rsp+88h+var_20], 1
0x1800072f6  jnz     short loc_180007302
0x1800072f8  mov     eax, 0C000000Dh
0x1800072fd  jmp     loc_180007444
0x180007302  test    ebp, ebp
0x180007304  jz      short loc_18000733A
0x180007306  mov     r9d, 4; ProcessInformationLength
0x18000730c  mov     [rsp+88h+ProcessInformation], 1
0x180007317  lea     r8, [rsp+88h+ProcessInformation]; ProcessInformation
0x18000731f  mov     rcx, rbx; ProcessHandle
0x180007322  lea     edx, [r9+0Fh]; ProcessInformationClass
0x180007326  call    cs:__imp_NtSetInformationProcess
0x18000732d  nop     dword ptr [rax+rax+00h]
0x180007332  test    eax, eax
0x180007334  js      loc_180007444
0x18000733a  mov     [rsp+88h+arg_8], rdi
0x180007342  mov     rdi, [rsp+88h+arg_20]
0x18000734a  test    esi, esi
0x18000734c  jnz     short loc_180007388
0x18000734e  test    dword ptr [rdi+5Ch], 2000h
0x180007355  jnz     short loc_180007388
0x180007357  mov     rax, cs:sxsFunctions
0x18000735e  test    rax, rax
0x180007361  jz      short loc_180007388
0x180007363  mov     r8, [rsp+88h+arg_48]
0x18000736b  test    r8, r8
0x18000736e  jz      short loc_180007388
0x180007370  mov     rcx, [rdi+50h]
0x180007374  mov     rdx, rbx
0x180007377  mov     rax, [rax+8]
0x18000737b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007380  test    eax, eax
0x180007382  js      loc_18000743C
0x180007388  neg     esi
0x18000738a  sbb     ecx, ecx
0x18000738c  and     ecx, 2000h
0x180007392  mov     edx, ecx
0x180007394  or      edx, 4
0x180007397  test    dword ptr [rsp+88h+arg_40], 200h
0x1800073a2  cmovz   edx, ecx
0x1800073a5  mov     ecx, edx
0x1800073a7  or      ecx, 20h
0x1800073aa  test    r14b, 2
0x1800073ae  cmovnz  ecx, edx
0x1800073b1  test    r15d, r15d
0x1800073b4  jz      short loc_1800073CE
0x1800073b6  mov     eax, r14d
0x1800073b9  and     eax, 1
0x1800073bc  shl     eax, 9
0x1800073bf  sub     eax, 0FFFFFF80h
0x1800073c2  or      ecx, eax
0x1800073c4  test    bpl, 0E0h
0x1800073c8  jz      short loc_1800073CE
0x1800073ca  bts     ecx, 0Ah
0x1800073ce  mov     r9, [rdi+30h]
0x1800073d2  mov     rdi, [rsp+88h+arg_38]
0x1800073da  mov     rdx, [rsp+88h+arg_30]
0x1800073e2  mov     r8, rdi
0x1800073e5  mov     [rsp+88h+var_60], 0
0x1800073ee  mov     [rsp+88h+var_68], ecx
0x1800073f2  mov     rcx, rbx
0x1800073f5  call    cs:__imp_CsrCreateProcess
0x1800073fc  nop     dword ptr [rax+rax+00h]
0x180007401  test    eax, eax
0x180007403  js      short loc_18000743C
0x180007405  mov     rcx, [rsp+88h+arg_50]
0x18000740d  mov     r10, cs:UserNotifyProcessCreate
0x180007414  mov     dword ptr [rcx], 0
0x18000741a  test    r10, r10
0x18000741d  jz      short loc_18000743C
0x18000741f  mov     ecx, [rdi]
0x180007421  mov     r9d, r14d
0x180007424  or      r9d, 10h
0x180007428  mov     rax, r10
0x18000742b  test    r15d, r15d
0x18000742e  cmovz   r9d, r14d
0x180007432  xor     r8d, r8d
0x180007435  xor     edx, edx
0x180007437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743c  mov     rdi, [rsp+88h+arg_8]
0x180007444  lea     r11, [rsp+88h+var_18]
0x180007449  mov     rbx, [r11+30h]
0x18000744d  mov     rbp, [r11+38h]
0x180007451  mov     rsp, r11
0x180007454  pop     r15
0x180007456  pop     r14
0x180007458  pop     rsi
0x180007459  retn
```
