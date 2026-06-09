# InternalBaseSrvCreateProcess

- ea: `0x180007580`
- end: `0x180007760`
- name: `InternalBaseSrvCreateProcess`
- size: `480`
- prototype: `NTSTATUS __fastcall(int, int, unsigned int, int, __int64, HANDLE ProcessHandle, __int64, unsigned int *, __int16, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007170`

## callees

- `0x180007580`
- `0x18000e010`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800075dd`
- `ntdll!NtQueryInformationProcess` at `0x1800075dd`
- `ntdll!NtSetInformationProcess` at `0x180007627`
- `ntdll!NtSetInformationProcess` at `0x180007627`
- `CSRSRV!CsrCreateProcess` at `0x1800076fa`
- `CSRSRV!CsrCreateProcess` at `0x1800076fa`

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
  __int64 v17; // rsi
  int v18; // edx
  int v19; // ecx
  int v20; // eax
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
    goto LABEL_27;
  v24[0] = 64;
  result = NtQueryInformationProcess(ProcessHandle, ProcessBasicInformation, v24, 0x40u, 0);
  if ( result < 0 )
    return result;
  if ( (BYTE8(v25) & 1) == 0 )
    return -1073741811;
LABEL_27:
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
        v20 = v19 | (((a3 & 1) << 9) + 128);
        if ( (a4 & 0xE0) != 0 )
          v20 |= 0x400u;
      }
      else
      {
        v20 = v19;
      }
      v21 = a8;
      result = CsrCreateProcess(v11, a7, a8, *(_QWORD *)(v17 + 48), v20, 0);
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
0x180007580  mov     rax, rsp
0x180007583  mov     [rax+18h], rbx
0x180007587  mov     [rax+20h], rbp
0x18000758b  push    rdi
0x18000758c  push    r14
0x18000758e  push    r15
0x180007590  sub     rsp, 70h
0x180007594  mov     rbx, [rsp+88h+ProcessHandle]
0x18000759c  xorps   xmm0, xmm0
0x18000759f  mov     ebp, r9d
0x1800075a2  mov     r14d, r8d
0x1800075a5  mov     r15d, edx
0x1800075a8  mov     edi, ecx
0x1800075aa  movups  xmmword ptr [rax-58h], xmm0
0x1800075ae  movups  xmmword ptr [rax-48h], xmm0
0x1800075b2  movups  xmmword ptr [rax-38h], xmm0
0x1800075b6  movups  xmmword ptr [rax-28h], xmm0
0x1800075ba  test    ecx, ecx
0x1800075bc  jz      short loc_180007602
0x1800075be  mov     r9d, 40h ; '@'; ProcessInformationLength
0x1800075c4  mov     qword ptr [rax-58h], 40h ; '@'
0x1800075cc  lea     r8, [rax-58h]; ProcessInformation
0x1800075d0  mov     qword ptr [rax-68h], 0
0x1800075d8  xor     edx, edx; ProcessInformationClass
0x1800075da  mov     rcx, rbx; ProcessHandle
0x1800075dd  call    cs:__imp_NtQueryInformationProcess
0x1800075e4  nop     dword ptr [rax+rax+00h]
0x1800075e9  test    eax, eax
0x1800075eb  js      loc_180007749
0x1800075f1  test    [rsp+88h+var_20], 1
0x1800075f6  jnz     short loc_180007602
0x1800075f8  mov     eax, 0C000000Dh
0x1800075fd  jmp     loc_180007749
0x180007602  test    ebp, ebp
0x180007604  jz      short loc_18000763B
0x180007606  mov     r9d, 4; ProcessInformationLength
0x18000760c  mov     [rsp+88h+ProcessInformation], 1
0x180007617  lea     r8, [rsp+88h+ProcessInformation]; ProcessInformation
0x18000761f  mov     edx, 13h; ProcessInformationClass
0x180007624  mov     rcx, rbx; ProcessHandle
0x180007627  call    cs:__imp_NtSetInformationProcess
0x18000762e  nop     dword ptr [rax+rax+00h]
0x180007633  test    eax, eax
0x180007635  js      loc_180007749
0x18000763b  mov     [rsp+88h+arg_8], rsi
0x180007643  mov     rsi, [rsp+88h+arg_20]
0x18000764b  test    edi, edi
0x18000764d  jnz     short loc_180007689
0x18000764f  test    dword ptr [rsi+5Ch], 2000h
0x180007656  jnz     short loc_180007689
0x180007658  mov     rax, cs:sxsFunctions
0x18000765f  test    rax, rax
0x180007662  jz      short loc_180007689
0x180007664  mov     r8, [rsp+88h+arg_48]
0x18000766c  test    r8, r8
0x18000766f  jz      short loc_180007689
0x180007671  mov     rcx, [rsi+50h]
0x180007675  mov     rdx, rbx
0x180007678  mov     rax, [rax+8]
0x18000767c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007681  test    eax, eax
0x180007683  js      loc_180007741
0x180007689  neg     edi
0x18000768b  sbb     ecx, ecx
0x18000768d  and     ecx, 2000h
0x180007693  mov     edx, ecx
0x180007695  or      edx, 4
0x180007698  test    dword ptr [rsp+88h+arg_40], 200h
0x1800076a3  cmovz   edx, ecx
0x1800076a6  mov     ecx, edx
0x1800076a8  or      ecx, 20h
0x1800076ab  test    r14b, 2
0x1800076af  cmovnz  ecx, edx
0x1800076b2  test    r15d, r15d
0x1800076b5  jz      short loc_1800076D1
0x1800076b7  mov     eax, r14d
0x1800076ba  and     eax, 1
0x1800076bd  shl     eax, 9
0x1800076c0  sub     eax, 0FFFFFF80h
0x1800076c3  or      eax, ecx
0x1800076c5  test    bpl, 0E0h
0x1800076c9  jz      short loc_1800076D3
0x1800076cb  bts     eax, 0Ah
0x1800076cf  jmp     short loc_1800076D3
0x1800076d1  mov     eax, ecx
0x1800076d3  mov     rdi, [rsp+88h+arg_38]
0x1800076db  mov     rcx, rbx
0x1800076de  mov     r9, [rsi+30h]
0x1800076e2  mov     r8, rdi
0x1800076e5  mov     rdx, [rsp+88h+arg_30]
0x1800076ed  mov     [rsp+88h+var_60], 0
0x1800076f6  mov     [rsp+88h+var_68], eax
0x1800076fa  call    cs:__imp_CsrCreateProcess
0x180007701  nop     dword ptr [rax+rax+00h]
0x180007706  test    eax, eax
0x180007708  js      short loc_180007741
0x18000770a  mov     rcx, [rsp+88h+arg_50]
0x180007712  mov     r10, cs:UserNotifyProcessCreate
0x180007719  mov     dword ptr [rcx], 0
0x18000771f  test    r10, r10
0x180007722  jz      short loc_180007741
0x180007724  mov     ecx, [rdi]
0x180007726  mov     r9d, r14d
0x180007729  or      r9d, 10h
0x18000772d  mov     rax, r10
0x180007730  test    r15d, r15d
0x180007733  cmovz   r9d, r14d
0x180007737  xor     r8d, r8d
0x18000773a  xor     edx, edx
0x18000773c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007741  mov     rsi, [rsp+88h+arg_8]
0x180007749  lea     r11, [rsp+88h+var_18]
0x18000774e  mov     rbx, [r11+30h]
0x180007752  mov     rbp, [r11+38h]
0x180007756  mov     rsp, r11
0x180007759  pop     r15
0x18000775b  pop     r14
0x18000775d  pop     rdi
0x18000775e  retn
```
