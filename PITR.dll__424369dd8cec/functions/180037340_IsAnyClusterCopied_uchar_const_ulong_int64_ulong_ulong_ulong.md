# IsAnyClusterCopied(uchar * const,ulong,__int64,ulong,ulong,ulong *)

- ea: `0x180037340`
- end: `0x1800374a6`
- name: `?IsAnyClusterCopied@@YAHQEAEK_JKKPEAK@Z`
- size: `358`
- prototype: `__int64 __fastcall(unsigned __int8 *const, int, __int64, unsigned int, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x180033ff4`
- `0x1800348d0`

## callees

- `0x180009e04`
- `0x180037340`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037417`
- `WDSCORE!CurrentIP` at `0x18003741f`
- `WDSCORE!CurrentIP` at `0x18003741f`
- `WDSCORE!WdsSetupLogMessageW` at `0x180037488`
- `WDSCORE!WdsSetupLogMessageW` at `0x180037488`

## string_xrefs

- `0x180037471`: `base\diagnosis\srt\pitr\dll\src\vssutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsAnyClusterCopied(
        unsigned __int8 *const a1,
        int a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6)
{
  unsigned int v6; // ebx
  unsigned int v9; // r11d
  unsigned int v10; // r14d
  __int64 v11; // rbp
  int v12; // r8d
  unsigned int v13; // r9d
  DWORD LastError; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax

  v6 = 0;
  if ( a6 )
    *a6 = 0;
  v9 = 0;
  v10 = 8 * a2;
  if ( a4 )
  {
    while ( 1 )
    {
      v11 = a5 * (a3 + v9) / 0x4000;
      if ( v11 >= v10 )
        break;
      v12 = 0;
      if ( a5 <= 0x4000 )
      {
        v13 = 1;
        goto LABEL_9;
      }
      v13 = a5 >> 14;
      if ( a5 >> 14 )
      {
LABEL_9:
        while ( ((unsigned __int8)(1 << ((v12 + v11) & 7)) & a1[(unsigned __int64)(unsigned int)(v12 + v11) >> 3]) == 0 )
        {
          if ( ++v12 >= v13 )
            goto LABEL_14;
        }
        v6 = 1;
        if ( !a6 )
          return v6;
        ++*a6;
      }
LABEL_14:
      if ( ++v9 >= a4 )
        return v6;
    }
    LastError = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(0x2000000, "Cluster bit in VSS is greater than the bitmap size: %I64d vs. %d", v11, v10);
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      886,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\vssutils.cpp",
      L"IsAnyClusterCopied",
      v15,
      LastError,
      0,
      0);
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180037340  mov     [rsp+arg_0], rcx
0x180037345  push    rbx
0x180037346  push    rbp
0x180037347  push    rsi
0x180037348  push    rdi
0x180037349  push    r12
0x18003734b  push    r13
0x18003734d  push    r14
0x18003734f  push    r15
0x180037351  sub     rsp, 68h
0x180037355  mov     r10, [rsp+0A8h+arg_28]
0x18003735d  xor     ebx, ebx
0x18003735f  mov     edi, [rsp+0A8h+arg_20]
0x180037366  mov     esi, r9d
0x180037369  mov     r13, r8
0x18003736c  test    r10, r10
0x18003736f  jz      short loc_180037374
0x180037371  mov     [r10], ebx
0x180037374  xor     r11d, r11d
0x180037377  lea     r14d, ds:0[rdx*8]
0x18003737f  test    esi, esi
0x180037381  jz      loc_180037493
0x180037387  mov     r15, rdi
0x18003738a  mov     r12d, r14d
0x18003738d  mov     eax, r11d
0x180037390  add     rax, r13
0x180037393  imul    rax, r15
0x180037397  cqo
0x180037399  and     edx, 3FFFh
0x18003739f  add     rax, rdx
0x1800373a2  sar     rax, 0Eh
0x1800373a6  mov     rbp, rax
0x1800373a9  cmp     rax, r12
0x1800373ac  jge     short loc_180037417
0x1800373ae  xor     r8d, r8d
0x1800373b1  cmp     edi, 4000h
0x1800373b7  jbe     short loc_1800373C7
0x1800373b9  mov     r9d, edi
0x1800373bc  shr     r9d, 0Eh
0x1800373c0  test    r9d, r9d
0x1800373c3  jz      short loc_180037409
0x1800373c5  jmp     short loc_1800373CD
0x1800373c7  mov     r9d, 1
0x1800373cd  lea     eax, [r8+rbp]
0x1800373d1  mov     edx, 1
0x1800373d6  mov     ecx, eax
0x1800373d8  shr     rax, 3
0x1800373dc  and     ecx, 7
0x1800373df  shl     dl, cl
0x1800373e1  mov     rcx, [rsp+0A8h+arg_0]
0x1800373e9  test    [rax+rcx], dl
0x1800373ec  jnz     short loc_1800373F8
0x1800373ee  inc     r8d
0x1800373f1  cmp     r8d, r9d
0x1800373f4  jb      short loc_1800373CD
0x1800373f6  jmp     short loc_180037409
0x1800373f8  mov     ebx, 1
0x1800373fd  test    r10, r10
0x180037400  jz      loc_180037493
0x180037406  inc     dword ptr [r10]
0x180037409  inc     r11d
0x18003740c  cmp     r11d, esi
0x18003740f  jb      loc_18003738D
0x180037415  jmp     short loc_180037493
0x180037417  call    cs:__imp_GetLastError
0x18003741d  mov     edi, eax
0x18003741f  call    cs:__imp_CurrentIP
0x180037425  mov     r9d, r14d
0x180037428  lea     rdx, aClusterBitInVs; "Cluster bit in VSS is greater than the "...
0x18003742f  mov     r8, rbp
0x180037432  mov     ecx, 2000000h; unsigned int
0x180037437  mov     rbx, rax
0x18003743a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003743f  mov     [rsp+0A8h+var_58], 0
0x180037447  lea     rcx, aIsanyclusterco; "IsAnyClusterCopied"
0x18003744e  mov     [rsp+0A8h+var_60], 0
0x180037457  lea     r8, aD; "D"
0x18003745e  mov     [rsp+0A8h+var_68], edi
0x180037462  xor     r9d, r9d
0x180037465  mov     [rsp+0A8h+var_70], rbx
0x18003746a  xor     edx, edx
0x18003746c  mov     [rsp+0A8h+var_78], rcx
0x180037471  lea     rcx, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\pitr\\dll\\src\\v"...
0x180037478  mov     [rsp+0A8h+var_80], rcx
0x18003747d  mov     rcx, rax
0x180037480  mov     [rsp+0A8h+var_88], 376h
0x180037488  call    cs:__imp_WdsSetupLogMessageW
0x18003748e  mov     ebx, 1
0x180037493  mov     eax, ebx
0x180037495  add     rsp, 68h
0x180037499  pop     r15
0x18003749b  pop     r14
0x18003749d  pop     r13
0x18003749f  pop     r12
0x1800374a1  pop     rdi
0x1800374a2  pop     rsi
0x1800374a3  pop     rbp
0x1800374a4  pop     rbx
0x1800374a5  retn
```
