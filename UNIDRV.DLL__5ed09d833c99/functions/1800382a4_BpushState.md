# BpushState

- ea: `0x1800382a4`
- end: `0x1800383fe`
- name: `BpushState`
- size: `346`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180043090`

## callees

- `0x180007150`
- `0x1800382a4`
- `0x180038404`
- `0x180045aa4`

## string_xrefs

- `0x180038362`: `OpenBrace encountered without accompanying construct keyword.`

## pseudocode

```c
__int64 __fastcall BpushState(unsigned int *a1, unsigned int a2, __int64 a3)
{
  __int64 v5; // r8
  int v6; // edx
  __int64 v7; // r8
  unsigned int v9; // edi

  v5 = *(unsigned int *)(a3 + 612);
  if ( (unsigned int)v5 < *(_DWORD *)(a3 + 608) )
  {
    v6 = dword_180078014[8 * *a1];
    if ( (_DWORD)v5 )
      v7 = *(unsigned int *)(*(_QWORD *)(a3 + 600) + 8LL * (unsigned int)(v5 - 1));
    else
      v7 = 0;
    if ( v6 <= 5 )
    {
      if ( v6 != 5 && v6 )
      {
        if ( v6 == 1 || v6 == 2 || (unsigned int)(v6 - 3) < 2 )
          return (unsigned int)BchangeState((__int64)a1, v6, v7, 1, a2, a3);
        return 1;
      }
    }
    else
    {
      if ( v6 == 6 || v6 == 7 || v6 == 8 )
        return (unsigned int)BchangeState((__int64)a1, v6, v7, 1, a2, a3);
      if ( v6 != 9 )
      {
        if ( v6 == 13 )
        {
          v9 = 0;
          vIdentifySource(a1, a3, v7);
          WriteDbgTraceErrorGpd((__int64)"BpushState", "OpenBrace encountered without accompanying construct keyword.");
          *(_DWORD *)(a3 + 2224) = 1;
          *(_DWORD *)(a3 + 2220) = 3;
          return v9;
        }
        return 1;
      }
    }
    return (unsigned int)BchangeState((__int64)a1, v6, v7, 0, a2, a3);
  }
  if ( *(int *)(a3 + 2220) < 2 )
  {
    WriteDbgTraceErrorGpd((__int64)"BpushState", "Exceeded max state stack depth.  Restarting", v5, a2);
    *(_DWORD *)(a3 + 2220) = 2;
    *(_DWORD *)(a3 + 2224) = 2;
    *(_DWORD *)(a3 + 2216) = 25;
  }
  return 0;
}

```

## disassembly

```asm
0x1800382a4  mov     [rsp+arg_0], rbx
0x1800382a9  push    rdi
0x1800382aa  sub     rsp, 30h
0x1800382ae  mov     rbx, r8
0x1800382b1  mov     r9d, edx
0x1800382b4  mov     r8d, [r8+264h]
0x1800382bb  mov     r10, rcx
0x1800382be  cmp     r8d, [rbx+260h]
0x1800382c5  jnb     short loc_180038332
0x1800382c7  mov     eax, [rcx]
0x1800382c9  lea     rdx, dword_180078014
0x1800382d0  shl     rax, 5
0x1800382d4  mov     edx, [rax+rdx]
0x1800382d7  test    r8d, r8d
0x1800382da  jz      short loc_18003832D
0x1800382dc  mov     rax, [rbx+258h]
0x1800382e3  lea     ecx, [r8-1]
0x1800382e7  mov     r8d, [rax+rcx*8]
0x1800382eb  cmp     edx, 5
0x1800382ee  jle     loc_1800383B6
0x1800382f4  mov     ecx, edx
0x1800382f6  sub     ecx, 6
0x1800382f9  jz      short loc_180038305
0x1800382fb  sub     ecx, 1
0x1800382fe  jz      short loc_180038305
0x180038300  sub     ecx, 1
0x180038303  jnz     short loc_180038343
0x180038305  mov     [rsp+38h+var_10], rbx
0x18003830a  mov     [rsp+38h+var_18], r9d
0x18003830f  mov     r9d, 1
0x180038315  mov     rcx, r10
0x180038318  call    BchangeState
0x18003831d  mov     edi, eax
0x18003831f  mov     eax, edi
0x180038321  mov     rbx, [rsp+38h+arg_0]
0x180038326  add     rsp, 30h
0x18003832a  pop     rdi
0x18003832b  retn
0x18003832d  xor     r8d, r8d
0x180038330  jmp     short loc_1800382EB
0x180038332  mov     edi, 2
0x180038337  cmp     [rbx+8ACh], edi
0x18003833d  jl      short loc_18003838B
0x18003833f  xor     eax, eax
0x180038341  jmp     short loc_180038321
0x180038343  sub     ecx, 1
0x180038346  jz      loc_1800383EC
0x18003834c  cmp     ecx, 4
0x18003834f  jnz     loc_1800383E2
0x180038355  mov     rdx, rbx
0x180038358  mov     rcx, r10
0x18003835b  xor     edi, edi
0x18003835d  call    vIdentifySource
0x180038362  lea     rdx, aOpenbraceEncou; "OpenBrace encountered without accompany"...
0x180038369  lea     rcx, aBpushstate; "BpushState"
0x180038370  call    WriteDbgTraceErrorGpd
0x180038375  mov     dword ptr [rbx+8B0h], 1
0x18003837f  mov     dword ptr [rbx+8ACh], 3
0x180038389  jmp     short loc_18003831F
0x18003838b  lea     rdx, aExceededMaxSta; "Exceeded max state stack depth.  Restar"...
0x180038392  lea     rcx, aBpushstate; "BpushState"
0x180038399  call    WriteDbgTraceErrorGpd
0x18003839e  mov     [rbx+8ACh], edi
0x1800383a4  mov     [rbx+8B0h], edi
0x1800383aa  mov     dword ptr [rbx+8A8h], 19h
0x1800383b4  jmp     short loc_18003833F
0x1800383b6  jz      short loc_1800383EC
0x1800383b8  mov     ecx, edx
0x1800383ba  test    edx, edx
0x1800383bc  jz      short loc_1800383EC
0x1800383be  sub     ecx, 1
0x1800383c1  jz      loc_180038305
0x1800383c7  sub     ecx, 1
0x1800383ca  jz      loc_180038305
0x1800383d0  sub     ecx, 1
0x1800383d3  jz      loc_180038305
0x1800383d9  cmp     ecx, 1
0x1800383dc  jz      loc_180038305
0x1800383e2  mov     edi, 1
0x1800383e7  jmp     loc_18003831F
0x1800383ec  mov     [rsp+38h+var_10], rbx
0x1800383f1  mov     [rsp+38h+var_18], r9d
0x1800383f6  xor     r9d, r9d
0x1800383f9  jmp     loc_180038315
```
