# CSingleSideReducer::CSingleSideReducer(double,bool)

- ea: `0x100436ff0`
- end: `0x10043713a`
- name: `??0CSingleSideReducer@@QEAA@N_N@Z`
- size: `330`
- prototype: `CSingleSideReducer *__fastcall(CSingleSideReducer *__hidden this, double, bool)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1004162a0`

## callees

- `0x100436ff0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CSingleSideReducer *__fastcall CSingleSideReducer::CSingleSideReducer(CSingleSideReducer *this, double a2, char a3)
{
  int v4; // eax
  char *v6; // [rsp+68h] [rbp+10h] BYREF
  char *v7; // [rsp+78h] [rbp+20h]

  *(_QWORD *)this = &CSingleSideReducer::`vftable';
  *((double *)this + 1) = a2;
  *((_BYTE *)this + 16) = a3;
  *((_QWORD *)this + 5) = 0;
  v6 = (char *)this + 48;
  *((_QWORD *)this + 6) = &CSimpleArea::`vftable';
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0x3FF0000000000000LL;
  *((_BYTE *)this + 96) = 0;
  *((_BYTE *)this + 105) = 0;
  *((_BYTE *)this + 106) = a2 < 0.0;
  v7 = (char *)this + 128;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 16) = 0;
  if ( g_SOSHost )
  {
    if ( (*(int (__fastcall **)(_QWORD, char **))(*g_SOSClerk + 80LL))(g_SOSClerk, &v6) < 0 )
    {
      if ( g_SOSHost )
        MEMORY[0] = 0;
      else
        (*(void (__fastcall **)(_QWORD, __int64, const char *, const char *, int, _QWORD, __int64))(MEMORY[0] + 528LL))(
          0,
          1,
          "SUCCEEDED(hr)",
          "sql\\ntdbms\\msql\\sysclrtypes\\spatial\\libraries\\geometry\\sqlmemblock.inl",
          77,
          0,
          -2);
    }
    v4 = 1024;
    if ( (unsigned __int64)v6 < 0x400 )
      v4 = (int)v6;
  }
  else
  {
    v4 = 4096;
  }
  *((_DWORD *)this + 37) = v4 / 0x48uLL;
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 48) = 0;
  return this;
}

```

## disassembly

```asm
0x100436ff0  mov     [rsp+arg_0], rcx
0x100436ff5  push    rbx
0x100436ff6  push    rsi
0x100436ff7  push    rdi
0x100436ff8  sub     rsp, 40h
0x100436ffc  mov     [rsp+58h+var_28], 0FFFFFFFFFFFFFFFEh
0x100437005  mov     rbx, rcx
0x100437008  lea     rax, ??_7CSingleSideReducer@@6B@; const CSingleSideReducer::`vftable'
0x10043700f  mov     [rcx], rax
0x100437012  movsd   qword ptr [rcx+8], xmm1
0x100437017  mov     [rcx+10h], r8b
0x10043701b  xor     esi, esi
0x10043701d  mov     [rcx+28h], rsi
0x100437021  lea     rax, [rcx+30h]
0x100437025  mov     [rsp+58h+arg_8], rax
0x10043702a  lea     rcx, ??_7CSimpleArea@@6B@; const CSimpleArea::`vftable'
0x100437031  mov     [rax], rcx
0x100437034  mov     [rax+8], rsi
0x100437038  mov     [rax+10h], rsi
0x10043703c  mov     rcx, 3FF0000000000000h
0x100437046  mov     [rax+18h], rcx
0x10043704a  mov     [rax+30h], sil
0x10043704e  mov     [rbx+69h], sil
0x100437052  xorps   xmm0, xmm0
0x100437055  comisd  xmm0, xmm1
0x100437059  setnbe  al
0x10043705c  mov     [rbx+6Ah], al
0x10043705f  lea     rdi, [rbx+80h]
0x100437066  mov     [rsp+58h+arg_18], rdi
0x10043706b  mov     [rdi+8], rsi
0x10043706f  mov     [rdi], rsi
0x100437072  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rsi; SOS_AutoHost g_SOSHost
0x100437079  jz      short loc_1004370E7
0x10043707b  mov     rcx, cs:?g_SOSClerk@@3VSOS_AutoMemClerk@@A; SOS_AutoMemClerk g_SOSClerk
0x100437082  mov     rax, [rcx]
0x100437085  lea     rdx, [rsp+58h+arg_8]
0x10043708a  call    qword ptr [rax+50h]
0x10043708d  test    eax, eax
0x10043708f  jns     short loc_1004370D3
0x100437091  cmp     cs:?g_SOSHost@@3VSOS_AutoHost@@A, rsi; SOS_AutoHost g_SOSHost
0x100437098  jz      short loc_1004370A3
0x10043709a  mov     ds:0, esi
0x1004370a1  jmp     short loc_1004370D3
0x1004370a3  mov     rax, ds:0
0x1004370ab  mov     [rsp+58h+var_30], rsi
0x1004370b0  mov     [rsp+58h+var_38], 4Dh ; 'M'
0x1004370b8  lea     r9, aSqlNtdbmsMsqlS_0; "sql\\ntdbms\\msql\\sysclrtypes\\spatial"...
0x1004370bf  lea     r8, aSucceededHr; "SUCCEEDED(hr)"
0x1004370c6  mov     edx, 1
0x1004370cb  xor     ecx, ecx
0x1004370cd  call    qword ptr [rax+210h]
0x1004370d3  mov     eax, 400h
0x1004370d8  mov     rcx, [rsp+58h+arg_8]
0x1004370dd  cmp     rcx, rax
0x1004370e0  jnb     short loc_1004370EC
0x1004370e2  mov     rax, rcx
0x1004370e5  jmp     short loc_1004370EC
0x1004370e7  mov     eax, 1000h
0x1004370ec  movsxd  rcx, eax
0x1004370ef  mov     rax, 0E38E38E38E38E38Fh
0x1004370f9  mul     rcx
0x1004370fc  shr     rdx, 6
0x100437100  mov     [rdi+14h], edx
0x100437103  mov     [rdi+10h], esi
0x100437106  mov     [rbx+98h], rsi
0x10043710d  mov     [rbx+0A8h], rsi
0x100437114  mov     [rbx+0A0h], rsi
0x10043711b  mov     [rbx+0B8h], rsi
0x100437122  mov     [rbx+0B0h], rsi
0x100437129  mov     [rbx+0C0h], esi
0x10043712f  mov     rax, rbx
0x100437132  add     rsp, 40h
0x100437136  pop     rdi
0x100437137  pop     rsi
0x100437138  pop     rbx
0x100437139  retn
```
