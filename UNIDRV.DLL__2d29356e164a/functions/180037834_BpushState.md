# BpushState

- ea: `0x180037834`
- end: `0x18003798d`
- name: `BpushState`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180041eec`

## callees

- `0x180007220`
- `0x180037834`
- `0x180037994`
- `0x18004485c`

## string_xrefs

- `0x1800378f1`: `OpenBrace encountered without accompanying construct keyword.`

## pseudocode

```c
__int64 __fastcall BpushState(unsigned int *a1, unsigned int a2, __int64 a3)
{
  __int64 v5; // r8
  int v6; // edx
  int v7; // r8d
  unsigned int v9; // edi

  v5 = *(unsigned int *)(a3 + 612);
  if ( (unsigned int)v5 < *(_DWORD *)(a3 + 608) )
  {
    v6 = dword_180076014[8 * *a1];
    if ( (_DWORD)v5 )
      v7 = *(_DWORD *)(*(_QWORD *)(a3 + 600) + 8LL * (unsigned int)(v5 - 1));
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
          vIdentifySource(a1, a3);
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
0x180037834  mov     [rsp+arg_0], rbx
0x180037839  push    rdi
0x18003783a  sub     rsp, 30h
0x18003783e  mov     rbx, r8
0x180037841  mov     r9d, edx
0x180037844  mov     r8d, [r8+264h]
0x18003784b  mov     r10, rcx
0x18003784e  cmp     r8d, [rbx+260h]
0x180037855  jnb     short loc_1800378C1
0x180037857  mov     eax, [rcx]
0x180037859  lea     rdx, dword_180076014
0x180037860  shl     rax, 5
0x180037864  mov     edx, [rax+rdx]
0x180037867  test    r8d, r8d
0x18003786a  jz      short loc_1800378BC
0x18003786c  mov     rax, [rbx+258h]
0x180037873  lea     ecx, [r8-1]
0x180037877  mov     r8d, [rax+rcx*8]
0x18003787b  cmp     edx, 5
0x18003787e  jle     loc_180037945
0x180037884  mov     ecx, edx
0x180037886  sub     ecx, 6
0x180037889  jz      short loc_180037895
0x18003788b  sub     ecx, 1
0x18003788e  jz      short loc_180037895
0x180037890  sub     ecx, 1
0x180037893  jnz     short loc_1800378D2
0x180037895  mov     [rsp+38h+var_10], rbx
0x18003789a  mov     [rsp+38h+var_18], r9d
0x18003789f  mov     r9d, 1
0x1800378a5  mov     rcx, r10
0x1800378a8  call    BchangeState
0x1800378ad  mov     edi, eax
0x1800378af  mov     eax, edi
0x1800378b1  mov     rbx, [rsp+38h+arg_0]
0x1800378b6  add     rsp, 30h
0x1800378ba  pop     rdi
0x1800378bb  retn
0x1800378bc  xor     r8d, r8d
0x1800378bf  jmp     short loc_18003787B
0x1800378c1  mov     edi, 2
0x1800378c6  cmp     [rbx+8ACh], edi
0x1800378cc  jl      short loc_18003791A
0x1800378ce  xor     eax, eax
0x1800378d0  jmp     short loc_1800378B1
0x1800378d2  sub     ecx, 1
0x1800378d5  jz      loc_18003797B
0x1800378db  cmp     ecx, 4
0x1800378de  jnz     loc_180037971
0x1800378e4  mov     rdx, rbx
0x1800378e7  mov     rcx, r10
0x1800378ea  xor     edi, edi
0x1800378ec  call    vIdentifySource
0x1800378f1  lea     rdx, aOpenbraceEncou; "OpenBrace encountered without accompany"...
0x1800378f8  lea     rcx, aBpushstate; "BpushState"
0x1800378ff  call    WriteDbgTraceErrorGpd
0x180037904  mov     dword ptr [rbx+8B0h], 1
0x18003790e  mov     dword ptr [rbx+8ACh], 3
0x180037918  jmp     short loc_1800378AF
0x18003791a  lea     rdx, aExceededMaxSta; "Exceeded max state stack depth.  Restar"...
0x180037921  lea     rcx, aBpushstate; "BpushState"
0x180037928  call    WriteDbgTraceErrorGpd
0x18003792d  mov     [rbx+8ACh], edi
0x180037933  mov     [rbx+8B0h], edi
0x180037939  mov     dword ptr [rbx+8A8h], 19h
0x180037943  jmp     short loc_1800378CE
0x180037945  jz      short loc_18003797B
0x180037947  mov     ecx, edx
0x180037949  test    edx, edx
0x18003794b  jz      short loc_18003797B
0x18003794d  sub     ecx, 1
0x180037950  jz      loc_180037895
0x180037956  sub     ecx, 1
0x180037959  jz      loc_180037895
0x18003795f  sub     ecx, 1
0x180037962  jz      loc_180037895
0x180037968  cmp     ecx, 1
0x18003796b  jz      loc_180037895
0x180037971  mov     edi, 1
0x180037976  jmp     loc_1800378AF
0x18003797b  mov     [rsp+38h+var_10], rbx
0x180037980  mov     [rsp+38h+var_18], r9d
0x180037985  xor     r9d, r9d
0x180037988  jmp     loc_1800378A5
```
