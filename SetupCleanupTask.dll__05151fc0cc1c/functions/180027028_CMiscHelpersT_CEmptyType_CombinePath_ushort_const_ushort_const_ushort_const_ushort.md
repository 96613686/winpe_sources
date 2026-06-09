# CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180027028`
- end: `0x180027136`
- name: `?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002b4ec`

## callees

- `0x180025124`
- `0x1800264f0`
- `0x180027008`
- `0x180027028`
- `0x1800275b8`
- `0x1800293a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027117`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027117`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027125`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027125`

## pseudocode

```c
__int64 __fastcall CMiscHelpersT<CEmptyType>::CombinePath(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // ecx
  __int64 v7; // rax
  void *v8; // rdi
  int StringCch; // eax
  void *v10; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID lpMem; // [rsp+20h] [rbp-18h] BYREF
  __int64 v14; // [rsp+28h] [rbp-10h]
  __int64 v15; // [rsp+70h] [rbp+38h] BYREF

  v15 = a3;
  lpMem = 0;
  v14 = 0;
  if ( a1
    && ((v4 = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::Append(
                &lpMem,
                a1),
         v5 = v4,
         v4 < 0)
     || (_DWORD)v14
     && (v7 = (unsigned int)(v14 - 1), *((_WORD *)lpMem + v7) != 92)
     && *((_WORD *)lpMem + v7) != 47
     && (v4 = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::Append(
                &lpMem,
                L"\\"),
         v5 = v4,
         v4 < 0))
    || a2
    && (v4 = CStringBufferImplT<unsigned short,CStringBufferPolicyDefaultT<unsigned short>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<unsigned short>>>::Append(
               &lpMem,
               a2),
        v5 = v4,
        v4 < 0) )
  {
    v6 = v4;
LABEL_16:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_17;
  }
  v8 = lpMem;
  if ( lpMem
    && (LODWORD(v15) = 0,
        StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(lpMem, &v15),
        v5 = StringCch,
        StringCch < 0)
    || (StringCch = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(v8),
        v5 = StringCch,
        StringCch < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
  {
    v6 = v5;
    goto LABEL_16;
  }
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  v10 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
  return v5;
}

```

## disassembly

```asm
0x180027028  mov     [rsp-20h+arg_10], r8
0x18002702d  push    rbp
0x18002702e  push    rbx
0x18002702f  push    rsi
0x180027030  push    rdi
0x180027031  mov     rbp, rsp
0x180027034  sub     rsp, 38h
0x180027038  mov     [rbp+lpMem], 0
0x180027040  mov     rsi, r9
0x180027043  mov     [rbp+var_10], 0
0x18002704b  mov     rdi, rdx
0x18002704e  test    rcx, rcx
0x180027051  jz      short loc_18002709D
0x180027053  mov     rdx, rcx
0x180027056  lea     rcx, [rbp+lpMem]
0x18002705a  call    ?Append@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBG@Z; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::Append(ushort const *)
0x18002705f  mov     ebx, eax
0x180027061  test    eax, eax
0x180027063  jns     short loc_18002706C
0x180027065  mov     ecx, eax
0x180027067  jmp     loc_180027102
0x18002706c  mov     eax, dword ptr [rbp+var_10]
0x18002706f  test    eax, eax
0x180027071  jz      short loc_18002709D
0x180027073  mov     rdx, [rbp+lpMem]
0x180027077  dec     eax
0x180027079  cmp     word ptr [rdx+rax*2], 5Ch ; '\'
0x18002707e  jz      short loc_18002709D
0x180027080  cmp     word ptr [rdx+rax*2], 2Fh ; '/'
0x180027085  jz      short loc_18002709D
0x180027087  lea     rdx, pszSrc; "\\"
0x18002708e  lea     rcx, [rbp+lpMem]
0x180027092  call    ?Append@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBG@Z; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::Append(ushort const *)
0x180027097  mov     ebx, eax
0x180027099  test    eax, eax
0x18002709b  js      short loc_180027065
0x18002709d  test    rdi, rdi
0x1800270a0  jz      short loc_1800270B4
0x1800270a2  mov     rdx, rdi
0x1800270a5  lea     rcx, [rbp+lpMem]
0x1800270a9  call    ?Append@?$CStringBufferImplT@GV?$CStringBufferPolicyDefaultT@G@@V?$CStringHelperDefaultT@V?$CStringBufferPolicyDefaultT@G@@@@@@QEAAJPEBG@Z; CStringBufferImplT<ushort,CStringBufferPolicyDefaultT<ushort>,CStringHelperDefaultT<CStringBufferPolicyDefaultT<ushort>>>::Append(ushort const *)
0x1800270ae  mov     ebx, eax
0x1800270b0  test    eax, eax
0x1800270b2  js      short loc_180027065
0x1800270b4  mov     rdi, [rbp+lpMem]
0x1800270b8  test    rdi, rdi
0x1800270bb  jnz     short loc_1800270C1
0x1800270bd  xor     edx, edx
0x1800270bf  jmp     short loc_1800270DD
0x1800270c1  lea     rdx, [rbp+arg_10]
0x1800270c5  mov     dword ptr [rbp+arg_10], 0
0x1800270cc  mov     rcx, rdi
0x1800270cf  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEBGPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(ushort const *,ulong *,ulong)
0x1800270d4  mov     ebx, eax
0x1800270d6  test    eax, eax
0x1800270d8  js      short loc_1800270EE
0x1800270da  mov     edx, dword ptr [rbp+arg_10]
0x1800270dd  mov     r8, rsi
0x1800270e0  mov     rcx, rdi; Src
0x1800270e3  call    ?CreateInternal@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@KAJPEBGKPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::CreateInternal(ushort const *,ulong,ushort * *)
0x1800270e8  mov     ebx, eax
0x1800270ea  test    eax, eax
0x1800270ec  jns     short loc_1800270F5
0x1800270ee  mov     ecx, eax
0x1800270f0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800270f5  mov     ecx, ebx
0x1800270f7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800270fc  test    ebx, ebx
0x1800270fe  jns     short loc_180027107
0x180027100  mov     ecx, ebx
0x180027102  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180027107  mov     ecx, ebx
0x180027109  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002710e  mov     rdi, [rbp+lpMem]
0x180027112  test    rdi, rdi
0x180027115  jz      short loc_18002712B
0x180027117  call    cs:__imp_GetProcessHeap
0x18002711d  mov     r8, rdi; lpMem
0x180027120  xor     edx, edx; dwFlags
0x180027122  mov     rcx, rax; hHeap
0x180027125  call    cs:__imp_HeapFree
0x18002712b  mov     eax, ebx
0x18002712d  add     rsp, 38h
0x180027131  pop     rdi
0x180027132  pop     rsi
0x180027133  pop     rbx
0x180027134  pop     rbp
0x180027135  retn
```
