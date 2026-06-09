# BinXmlVariantHolder::operator=(BinXmlVariant const &)

- ea: `0x180030214`
- end: `0x1800303ca`
- name: `??4BinXmlVariantHolder@@QEAAAEAV0@AEBUBinXmlVariant@@@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180027f4c`

## callees

- `0x18000a020`
- `0x18000b6a0`
- `0x180023548`
- `0x180030214`
- `0x180038fb4`
- `0x180038fcc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180030363`
- `api-ms-win-crt-private-l1-1-0!_o_strncpy_s` at `0x180030363`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003027f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003027f`

## pseudocode

```c
__int64 __fastcall BinXmlVariantHolder::operator=(__int64 a1, const void **a2)
{
  unsigned int v4; // eax
  HLOCAL v5; // rax
  _OWORD *v6; // rax
  unsigned int v7; // eax
  __int64 v8; // rax
  void *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rax
  void *v12; // rax
  __int64 v13; // r8
  __int128 pExceptionObject; // [rsp+20h] [rbp-38h] BYREF
  __int64 v16; // [rsp+30h] [rbp-28h]
  int v17; // [rsp+38h] [rbp-20h]
  int v18; // [rsp+3Ch] [rbp-1Ch]
  int v19; // [rsp+40h] [rbp-18h]

  BinXmlVariantHolder::Clear((void **)a1);
  switch ( *((_DWORD *)a2 + 3) )
  {
    case 1:
      v11 = *((unsigned int *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v11;
      v12 = operator new(saturated_mul(v11 + 1, 2u));
      v13 = *(unsigned int *)(a1 + 8);
      *(_QWORD *)a1 = v12;
      memcpy_0(v12, *a2, 2 * v13);
      *(_WORD *)(*(_QWORD *)a1 + 2LL * *(unsigned int *)(a1 + 8)) = 0;
      goto LABEL_19;
    case 2:
      v8 = *((unsigned int *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v8;
      v9 = operator new(v8 + 1);
      v10 = *(unsigned int *)(a1 + 8);
      *(_QWORD *)a1 = v9;
      _o_strncpy_s(v9, v10 + 1, *a2);
      goto LABEL_19;
    case 0xE:
      v7 = *((_DWORD *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v7;
      v5 = operator new(v7);
      *(_QWORD *)a1 = v5;
LABEL_16:
      memcpy_0(v5, *a2, *(unsigned int *)(a1 + 8));
      goto LABEL_19;
    case 0xF:
    case 0x12:
      *(_DWORD *)(a1 + 8) = -1;
      v6 = operator new(0x10u);
      *(_QWORD *)a1 = v6;
      *v6 = *(_OWORD *)*a2;
      goto LABEL_19;
    case 0x13:
      v4 = *((_DWORD *)a2 + 2);
      *(_DWORD *)(a1 + 8) = v4;
      v5 = LocalAlloc(0, v4);
      *(_QWORD *)a1 = v5;
      if ( !v5 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids, 14);
        }
        v16 = 0;
        v17 = 14;
        v18 = -1;
        pExceptionObject = 0;
        v19 = 59;
        throw (EvtException *)&pExceptionObject;
      }
      goto LABEL_16;
  }
  *(_DWORD *)(a1 + 8) = -1;
  *(_QWORD *)a1 = *a2;
LABEL_19:
  *(_DWORD *)(a1 + 12) = *((_DWORD *)a2 + 3);
  return a1;
}

```

## disassembly

```asm
0x180030214  mov     [rsp+arg_0], rbx
0x180030219  mov     [rsp+arg_8], rsi
0x18003021e  push    rdi
0x18003021f  sub     rsp, 50h
0x180030223  mov     rdi, rdx
0x180030226  mov     rbx, rcx
0x180030229  call    ?Clear@BinXmlVariantHolder@@QEAAXXZ; BinXmlVariantHolder::Clear(void)
0x18003022e  mov     ecx, [rdi+0Ch]
0x180030231  sub     ecx, 1
0x180030234  jz      loc_18003036B
0x18003023a  sub     ecx, 1
0x18003023d  jz      loc_180030343
0x180030243  sub     ecx, 0Ch
0x180030246  jz      loc_180030322
0x18003024c  sub     ecx, 1
0x18003024f  jz      loc_1800302FF
0x180030255  sub     ecx, 3
0x180030258  jz      loc_1800302FF
0x18003025e  cmp     ecx, 1
0x180030261  jz      short loc_180030275
0x180030263  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18003026a  mov     rax, [rdi]
0x18003026d  mov     [rbx], rax
0x180030270  jmp     loc_1800303B1
0x180030275  mov     eax, [rdi+8]
0x180030278  xor     ecx, ecx; uFlags
0x18003027a  mov     edx, eax; uBytes
0x18003027c  mov     [rbx+8], eax
0x18003027f  call    cs:__imp_LocalAlloc
0x180030285  xor     esi, esi
0x180030287  mov     [rbx], rax
0x18003028a  test    rax, rax
0x18003028d  jnz     loc_180030332
0x180030293  mov     rcx, cs:WPP_GLOBAL_Control
0x18003029a  lea     rax, WPP_GLOBAL_Control
0x1800302a1  lea     ebx, [rsi+0Eh]
0x1800302a4  cmp     rcx, rax
0x1800302a7  jz      short loc_1800302CB
0x1800302a9  test    byte ptr [rcx+1Ch], 2
0x1800302ad  jz      short loc_1800302CB
0x1800302af  cmp     byte ptr [rcx+19h], 2
0x1800302b3  jb      short loc_1800302CB
0x1800302b5  mov     rcx, [rcx+10h]
0x1800302b9  lea     edx, [rsi+0Ah]
0x1800302bc  mov     r9d, ebx
0x1800302bf  lea     r8, WPP_ee379fc095b93d44bb4c0c8f5551b3ef_Traceguids
0x1800302c6  call    WPP_SF_D
0x1800302cb  xorps   xmm0, xmm0
0x1800302ce  mov     [rsp+58h+var_28], rsi
0x1800302d3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800302da  mov     [rsp+58h+var_20], ebx
0x1800302de  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800302e3  mov     [rsp+58h+var_1C], 0FFFFFFFFh
0x1800302eb  movdqu  [rsp+58h+pExceptionObject], xmm0
0x1800302f1  mov     [rsp+58h+var_18], 3Bh ; ';'
0x1800302f9  call    _CxxThrowException_0
0x1800302ff  mov     ecx, 10h; dwBytes
0x180030304  mov     dword ptr [rbx+8], 0FFFFFFFFh
0x18003030b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030310  mov     [rbx], rax
0x180030313  mov     rcx, [rdi]
0x180030316  movups  xmm0, xmmword ptr [rcx]
0x180030319  movdqu  xmmword ptr [rax], xmm0
0x18003031d  jmp     loc_1800303B1
0x180030322  mov     eax, [rdi+8]
0x180030325  mov     ecx, eax; dwBytes
0x180030327  mov     [rbx+8], eax
0x18003032a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003032f  mov     [rbx], rax
0x180030332  mov     r8d, [rbx+8]; Size
0x180030336  mov     rcx, rax; void *
0x180030339  mov     rdx, [rdi]; Src
0x18003033c  call    memcpy_0
0x180030341  jmp     short loc_1800303B1
0x180030343  mov     eax, [rdi+8]
0x180030346  mov     [rbx+8], eax
0x180030349  lea     rcx, [rax+1]; dwBytes
0x18003034d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030352  mov     r9d, [rbx+8]
0x180030356  mov     rcx, rax
0x180030359  mov     [rbx], rax
0x18003035c  mov     r8, [rdi]
0x18003035f  lea     rdx, [r9+1]
0x180030363  call    cs:__imp__o_strncpy_s
0x180030369  jmp     short loc_1800303B1
0x18003036b  mov     eax, [rdi+8]
0x18003036e  mov     [rbx+8], eax
0x180030371  lea     rcx, [rax+1]
0x180030375  mov     eax, 2
0x18003037a  mul     rcx
0x18003037d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180030384  cmovb   rax, rcx
0x180030388  mov     rcx, rax; dwBytes
0x18003038b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180030390  mov     r8d, [rbx+8]
0x180030394  mov     rcx, rax; void *
0x180030397  mov     [rbx], rax
0x18003039a  add     r8, r8; Size
0x18003039d  mov     rdx, [rdi]; Src
0x1800303a0  call    memcpy_0
0x1800303a5  mov     ecx, [rbx+8]
0x1800303a8  xor     esi, esi
0x1800303aa  mov     rax, [rbx]
0x1800303ad  mov     [rax+rcx*2], si
0x1800303b1  mov     eax, [rdi+0Ch]
0x1800303b4  mov     rsi, [rsp+58h+arg_8]
0x1800303b9  mov     [rbx+0Ch], eax
0x1800303bc  mov     rax, rbx
0x1800303bf  mov     rbx, [rsp+58h+arg_0]
0x1800303c4  add     rsp, 50h
0x1800303c8  pop     rdi
0x1800303c9  retn
```
