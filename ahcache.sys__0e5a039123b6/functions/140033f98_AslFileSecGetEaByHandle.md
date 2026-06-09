# AslFileSecGetEaByHandle

- ea: `0x140033f98`
- end: `0x1400341aa`
- name: `AslFileSecGetEaByHandle`
- size: `530`
- prototype: `__int64 __fastcall(void *, unsigned int *, __int64, char *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14002dffc`
- `0x1400341b0`

## callees

- `0x1400079f0`
- `0x140007b40`
- `0x140007e40`
- `0x140033f98`
- `0x14003e364`
- `0x140045d44`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!ZwQueryEaFile` at `0x1400340d0`
- `ntoskrnl!ZwQueryEaFile` at `0x1400340d0`

## string_xrefs

- `0x140034077`: `$KERNEL.PURGE.AHC_READ_TIME`

## pseudocode

```c
__int64 __fastcall AslFileSecGetEaByHandle(void *a1, unsigned int *a2, __int64 a3, char *a4)
{
  unsigned int v8; // ebp
  __int64 v9; // rcx
  ULONG v10; // edi
  __int64 v11; // rax
  __int64 v12; // rsi
  unsigned int v13; // ebx
  _BYTE *v14; // rbx
  NTSTATUS v15; // eax
  __int64 v16; // rcx
  NTSTATUS v17; // edi
  unsigned int v18; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-1E8h] BYREF
  _DWORD EaList[68]; // [rsp+60h] [rbp-1D8h] BYREF
  _BYTE v21[128]; // [rsp+170h] [rbp-C8h] BYREF

  if ( !a1 )
    return 3221225711LL;
  if ( !a2 )
    return 3221225712LL;
  v8 = *a2;
  if ( !*a2 )
    return 3221225712LL;
  if ( (unsigned __int64)(a4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    IoStatusBlock = 0;
    memset(v21, 0, sizeof(v21));
    memset(EaList, 0, 0x105u);
    memset(a1, 0, v8);
    v10 = v8 + 39;
    *a2 = 0;
    if ( v8 + 39 <= 0x80 )
    {
      v12 = 0;
      v14 = v21;
      v10 = 128;
    }
    else
    {
      v11 = AslAlloc(v9, v10, 1);
      v12 = v11;
      if ( !v11 )
        return (unsigned int)-1073741801;
      v14 = (_BYTE *)v11;
    }
    strcpy((char *)&EaList[1] + 1, "$KERNEL.PURGE.AHC_READ_TIME");
    EaList[0] = 0;
    LOBYTE(EaList[1]) = 27;
    v15 = ZwQueryEaFile(a4, &IoStatusBlock, v14, v10, 0, EaList, 0x105u, 0, 1u);
    v17 = v15;
    if ( v15 >= 0 )
    {
      v18 = *((unsigned __int16 *)v14 + 3);
      if ( (_WORD)v18 )
      {
        *a2 = v18;
        if ( *((unsigned __int16 *)v14 + 3) > v8 )
        {
          v13 = -1073741789;
        }
        else
        {
          memmove(a1, &v14[(unsigned __int8)v14[5] + 9], *((unsigned __int16 *)v14 + 3));
          v13 = 0;
        }
      }
      else
      {
        v13 = -1073741275;
      }
    }
    else
    {
      v13 = -1073741275;
      if ( v15 != -1073741742 )
      {
        if ( v15 != -1073741275 && v15 != -1073741745 && v15 != -2147483643 )
          AslLogCallPrintf(1, "AslFileSecGetEaByHandle", 366, "ZwQueryEaFile failed 0x%08lx\n", v15);
        v13 = v17;
      }
    }
    if ( v12 )
      AslFree(v16, v12);
    return v13;
  }
  return 3221225480LL;
}

```

## disassembly

```asm
0x140033f98  mov     [rsp+arg_10], rbx
0x140033f9d  push    rbp
0x140033f9e  push    rsi
0x140033f9f  push    rdi
0x140033fa0  push    r12
0x140033fa2  push    r13
0x140033fa4  push    r14
0x140033fa6  push    r15
0x140033fa8  sub     rsp, 200h
0x140033faf  mov     rax, cs:__security_cookie
0x140033fb6  xor     rax, rsp
0x140033fb9  mov     [rsp+238h+var_48], rax
0x140033fc1  xor     r12d, r12d
0x140033fc4  mov     r13, r9
0x140033fc7  mov     r14, rdx
0x140033fca  mov     r15, rcx
0x140033fcd  test    rcx, rcx
0x140033fd0  jnz     short loc_140033FDC
0x140033fd2  mov     eax, 0C00000EFh
0x140033fd7  jmp     loc_14003417E
0x140033fdc  test    r14, r14
0x140033fdf  jz      loc_140034179
0x140033fe5  mov     ebp, [rdx]
0x140033fe7  test    ebp, ebp
0x140033fe9  jz      loc_140034179
0x140033fef  lea     rax, [r9-1]
0x140033ff3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140033ff7  ja      loc_140034172
0x140033ffd  xorps   xmm0, xmm0
0x140034000  lea     rcx, [rsp+238h+var_C8]; void *
0x140034008  mov     ebx, 80h
0x14003400d  xor     edx, edx; Val
0x14003400f  mov     r8d, ebx; Size
0x140034012  movups  xmmword ptr [rsp+238h+IoStatusBlock], xmm0
0x140034017  call    memset
0x14003401c  xor     edx, edx; Val
0x14003401e  lea     rcx, [rsp+238h+var_1D8]; void *
0x140034023  mov     r8d, 105h; Size
0x140034029  call    memset
0x14003402e  mov     r8d, ebp; Size
0x140034031  xor     edx, edx; Val
0x140034033  mov     rcx, r15; void *
0x140034036  call    memset
0x14003403b  lea     edi, [rbp+27h]
0x14003403e  mov     [r14], r12d
0x140034041  cmp     edi, ebx
0x140034043  jbe     short loc_140034067
0x140034045  mov     edx, edi
0x140034047  lea     r8d, [rbx-7Fh]
0x14003404b  call    AslAlloc
0x140034050  mov     rsi, rax
0x140034053  test    rax, rax
0x140034056  jnz     short loc_140034062
0x140034058  mov     ebx, 0C0000017h
0x14003405d  jmp     loc_14003416E
0x140034062  mov     rbx, rax
0x140034065  jmp     short loc_140034077
0x140034067  mov     rsi, r12
0x14003406a  lea     rbx, [rsp+238h+var_C8]
0x140034072  mov     edi, 80h
0x140034077  movups  xmm0, xmmword ptr cs:Str1; "$KERNEL.PURGE.AHC_READ_TIME"
0x14003407e  mov     [rsp+238h+RestartScan], 1; RestartScan
0x140034083  lea     rax, [rsp+238h+var_1D8]
0x140034088  movups  xmm1, xmmword ptr cs:Str1+0Bh; "GE.AHC_READ_TIME"
0x14003408f  mov     [rsp+238h+EaIndex], r12; EaIndex
0x140034094  lea     rdx, [rsp+238h+IoStatusBlock]; IoStatusBlock
0x140034099  mov     [rsp+238h+EaListLength], 105h; EaListLength
0x1400340a1  mov     r9d, edi; Length
0x1400340a4  movups  xmmword ptr [rsp+238h+var_1D3], xmm0
0x1400340a9  mov     [rsp+238h+EaList], rax; EaList
0x1400340ae  mov     r8, rbx; Buffer
0x1400340b1  mov     rcx, r13; FileHandle
0x1400340b4  mov     [rsp+238h+var_1D8], r12d
0x1400340b9  movups  xmmword ptr [rsp+238h+var_1D3+0Bh], xmm1
0x1400340be  mov     [rsp+238h+var_1D4], 1Bh
0x1400340c3  mov     [rsp+238h+var_1D3+1Bh], r12b
0x1400340cb  mov     [rsp+238h+ReturnSingleEntry], r12b; ReturnSingleEntry
0x1400340d0  call    cs:__imp_ZwQueryEaFile
0x1400340d7  nop     dword ptr [rax+rax+00h]
0x1400340dc  mov     edi, eax
0x1400340de  test    eax, eax
0x1400340e0  jns     short loc_140034126
0x1400340e2  mov     ebx, 0C0000225h
0x1400340e7  cmp     eax, 0C0000052h
0x1400340ec  jz      short loc_140034161
0x1400340ee  cmp     eax, ebx
0x1400340f0  jz      short loc_140034122
0x1400340f2  cmp     eax, 0C000004Fh
0x1400340f7  jz      short loc_140034122
0x1400340f9  cmp     eax, 80000005h
0x1400340fe  jz      short loc_140034122
0x140034100  lea     r9, aZwqueryeafileF; "ZwQueryEaFile failed 0x%08lx\n"
0x140034107  mov     dword ptr [rsp+238h+ReturnSingleEntry], eax
0x14003410b  mov     r8d, 16Eh
0x140034111  lea     rdx, aAslfilesecgete; "AslFileSecGetEaByHandle"
0x140034118  mov     ecx, 1
0x14003411d  call    AslLogCallPrintf
0x140034122  mov     ebx, edi
0x140034124  jmp     short loc_140034161
0x140034126  movzx   eax, word ptr [rbx+6]
0x14003412a  test    ax, ax
0x14003412d  jnz     short loc_140034136
0x14003412f  mov     ebx, 0C0000225h
0x140034134  jmp     short loc_140034161
0x140034136  mov     [r14], eax
0x140034139  movzx   eax, word ptr [rbx+6]
0x14003413d  cmp     eax, ebp
0x14003413f  ja      short loc_14003415C
0x140034141  movzx   edx, byte ptr [rbx+5]
0x140034145  mov     r8d, eax; Size
0x140034148  add     rdx, 9
0x14003414c  mov     rcx, r15; void *
0x14003414f  add     rdx, rbx; Src
0x140034152  call    memmove
0x140034157  mov     ebx, r12d
0x14003415a  jmp     short loc_140034161
0x14003415c  mov     ebx, 0C0000023h
0x140034161  test    rsi, rsi
0x140034164  jz      short loc_14003416E
0x140034166  mov     rdx, rsi
0x140034169  call    AslFree
0x14003416e  mov     eax, ebx
0x140034170  jmp     short loc_14003417E
0x140034172  mov     eax, 0C0000008h
0x140034177  jmp     short loc_14003417E
0x140034179  mov     eax, 0C00000F0h
0x14003417e  mov     rcx, [rsp+238h+var_48]
0x140034186  xor     rcx, rsp; StackCookie
0x140034189  call    __security_check_cookie
0x14003418e  mov     rbx, [rsp+238h+arg_10]
0x140034196  add     rsp, 200h
0x14003419d  pop     r15
0x14003419f  pop     r14
0x1400341a1  pop     r13
0x1400341a3  pop     r12
0x1400341a5  pop     rdi
0x1400341a6  pop     rsi
0x1400341a7  pop     rbp
0x1400341a8  retn
```
