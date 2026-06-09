# CWinPidRegistryInfoT<CEmptyType>::GetPid4(ushort const *,DIGITALPID4 *)

- ea: `0x180021f60`
- end: `0x180022081`
- name: `?GetPid4@?$CWinPidRegistryInfoT@VCEmptyType@@@@SAJPEBGPEAUDIGITALPID4@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(__int64, _OWORD *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180022088`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x180018b40`
- `0x180021f60`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022069`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180022069`

## pseudocode

```c
__int64 __fastcall CWinPidRegistryInfoT<CEmptyType>::GetPid4(__int64 a1, _OWORD *a2, int a3)
{
  _OWORD *v3; // rbx
  int Value; // eax
  HLOCAL v5; // rsi
  unsigned int v6; // edi
  int v7; // ecx
  __int64 v8; // rcx
  _OWORD *v9; // rax
  __int128 v10; // xmm1
  int v12; // [rsp+40h] [rbp+8h] BYREF
  int v13; // [rsp+44h] [rbp+Ch]
  HLOCAL hMem; // [rsp+50h] [rbp+18h] BYREF

  v13 = HIDWORD(a1);
  hMem = 0;
  v3 = a2;
  v12 = 0;
  Value = CRegUtilT<void *,CRegType,0,1>::GetValue(a1, (_DWORD)a2, a3, (unsigned int)&hMem, (__int64)&v12);
  v5 = hMem;
  v6 = Value;
  if ( Value < 0 )
  {
    v7 = Value;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_10;
  }
  if ( v12 != 1272 || *(_DWORD *)hMem != 1272 )
  {
    v7 = -2147024883;
    v6 = -2147024883;
    goto LABEL_3;
  }
  v8 = 9;
  v9 = hMem;
  do
  {
    *v3 = *v9;
    v3[1] = v9[1];
    v3[2] = v9[2];
    v3[3] = v9[3];
    v3[4] = v9[4];
    v3[5] = v9[5];
    v3[6] = v9[6];
    v10 = v9[7];
    v9 += 8;
    v3[7] = v10;
    v3 += 8;
    --v8;
  }
  while ( v8 );
  *v3 = *v9;
  v3[1] = v9[1];
  v3[2] = v9[2];
  v3[3] = v9[3];
  v3[4] = v9[4];
  v3[5] = v9[5];
  v3[6] = v9[6];
  *((_QWORD *)v3 + 14) = *((_QWORD *)v9 + 14);
LABEL_10:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v5 )
    LocalFree(v5);
  return v6;
}

```

## disassembly

```asm
0x180021f60  mov     r11, rsp
0x180021f63  mov     [r11+10h], rbx
0x180021f67  mov     [r11+20h], rsi
0x180021f6b  mov     [r11+8], rcx
0x180021f6f  push    rdi
0x180021f70  sub     rsp, 30h
0x180021f74  lea     rax, [r11+8]
0x180021f78  mov     qword ptr [r11+18h], 0
0x180021f80  lea     r9, [r11+18h]
0x180021f84  mov     [r11-18h], rax
0x180021f88  mov     rbx, rdx
0x180021f8b  mov     [rsp+38h+arg_0], 0
0x180021f93  call    ?GetValue@?$CRegUtilT@PEAXUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEBG1PEAPEAXPEAK@Z; CRegUtilT<void *,CRegType,0,1>::GetValue(HKEY__ *,ushort const *,ushort const *,void * *,ulong *)
0x180021f98  mov     rsi, [rsp+38h+hMem]
0x180021f9d  mov     edi, eax
0x180021f9f  test    eax, eax
0x180021fa1  jns     short loc_180021FAF
0x180021fa3  mov     ecx, eax
0x180021fa5  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180021faa  jmp     loc_18002205A
0x180021faf  mov     eax, 4F8h
0x180021fb4  cmp     [rsp+38h+arg_0], eax
0x180021fb8  jz      short loc_180021FC3
0x180021fba  mov     ecx, 8007000Dh
0x180021fbf  mov     edi, ecx
0x180021fc1  jmp     short loc_180021FA5
0x180021fc3  cmp     [rsi], eax
0x180021fc5  jnz     short loc_180021FBA
0x180021fc7  mov     ecx, 9
0x180021fcc  mov     rax, rsi
0x180021fcf  lea     edx, [rcx+77h]
0x180021fd2  movups  xmm0, xmmword ptr [rax]
0x180021fd5  movups  xmmword ptr [rbx], xmm0
0x180021fd8  movups  xmm1, xmmword ptr [rax+10h]
0x180021fdc  movups  xmmword ptr [rbx+10h], xmm1
0x180021fe0  movups  xmm0, xmmword ptr [rax+20h]
0x180021fe4  movups  xmmword ptr [rbx+20h], xmm0
0x180021fe8  movups  xmm1, xmmword ptr [rax+30h]
0x180021fec  movups  xmmword ptr [rbx+30h], xmm1
0x180021ff0  movups  xmm0, xmmword ptr [rax+40h]
0x180021ff4  movups  xmmword ptr [rbx+40h], xmm0
0x180021ff8  movups  xmm1, xmmword ptr [rax+50h]
0x180021ffc  movups  xmmword ptr [rbx+50h], xmm1
0x180022000  movups  xmm0, xmmword ptr [rax+60h]
0x180022004  movups  xmmword ptr [rbx+60h], xmm0
0x180022008  movups  xmm1, xmmword ptr [rax+70h]
0x18002200c  add     rax, rdx
0x18002200f  movups  xmmword ptr [rbx+70h], xmm1
0x180022013  add     rbx, rdx
0x180022016  sub     rcx, 1
0x18002201a  jnz     short loc_180021FD2
0x18002201c  movups  xmm0, xmmword ptr [rax]
0x18002201f  movups  xmmword ptr [rbx], xmm0
0x180022022  movups  xmm1, xmmword ptr [rax+10h]
0x180022026  movups  xmmword ptr [rbx+10h], xmm1
0x18002202a  movups  xmm0, xmmword ptr [rax+20h]
0x18002202e  movups  xmmword ptr [rbx+20h], xmm0
0x180022032  movups  xmm1, xmmword ptr [rax+30h]
0x180022036  movups  xmmword ptr [rbx+30h], xmm1
0x18002203a  movups  xmm0, xmmword ptr [rax+40h]
0x18002203e  movups  xmmword ptr [rbx+40h], xmm0
0x180022042  movups  xmm1, xmmword ptr [rax+50h]
0x180022046  movups  xmmword ptr [rbx+50h], xmm1
0x18002204a  movups  xmm0, xmmword ptr [rax+60h]
0x18002204e  movups  xmmword ptr [rbx+60h], xmm0
0x180022052  mov     rax, [rax+70h]
0x180022056  mov     [rbx+70h], rax
0x18002205a  mov     ecx, edi
0x18002205c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180022061  test    rsi, rsi
0x180022064  jz      short loc_18002206F
0x180022066  mov     rcx, rsi; hMem
0x180022069  call    cs:__imp_LocalFree
0x18002206f  mov     rbx, [rsp+38h+arg_8]
0x180022074  mov     eax, edi
0x180022076  mov     rsi, [rsp+38h+arg_18]
0x18002207b  add     rsp, 30h
0x18002207f  pop     rdi
0x180022080  retn
```
