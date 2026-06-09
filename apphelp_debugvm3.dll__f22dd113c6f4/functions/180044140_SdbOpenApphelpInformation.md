# SdbOpenApphelpInformation

- ea: `0x180044140`
- end: `0x18004438f`
- name: `SdbOpenApphelpInformation`
- size: `591`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180002be0`
- `0x18000f114`
- `0x180011dc0`
- `0x180015fb0`
- `0x180018f20`
- `0x180044140`
- `0x180045f90`
- `0x180048668`
- `0x18004b104`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800442a0`
- `ntdll!RtlAllocateHeap` at `0x1800442a0`

## string_xrefs

- `0x18004431f`: `Failed to resolve database path`
- `0x1800441bb`: `SdbOpenApphelpInformation`
- `0x180044244`: `SdbOpenApphelpInformation`
- `0x18004432c`: `SdbOpenApphelpInformation`
- `0x18004423d`: `Failed to open database "%ws"`
- `0x18004430d`: `Error reading apphelp basic information, apphelp may not be present for tagid 0x%lx`

## pseudocode

```c
_QWORD *__fastcall SdbOpenApphelpInformation(__int128 *a1, _OWORD *a2)
{
  _QWORD *v4; // rbx
  _QWORD *inited; // rdi
  __int64 v6; // r14
  int FirstGUIDIndexedTag; // esi
  _QWORD *Heap; // rax
  __int128 v9; // xmm1
  __int64 v11; // [rsp+20h] [rbp-E0h]
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+34h] [rbp-CCh] BYREF
  _OWORD v14[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+58h] [rbp-A8h]
  _BYTE v16[528]; // [rsp+60h] [rbp-A0h] BYREF

  v12 = 0;
  v15 = 0;
  v4 = 0;
  memset(v14, 0, sizeof(v14));
  inited = (_QWORD *)SdbInitDatabaseEx(4, 0, 332);
  if ( inited )
  {
    if ( (unsigned int)SdbResolveDatabaseEx((_DWORD)inited, (_DWORD)a1, (unsigned int)&v12, 0, (__int64)v16, 260) - 1 > 0x103 )
    {
      AslLogCallPrintf(1, "SdbOpenApphelpInformation", 2373, "Failed to resolve database path");
    }
    else
    {
      v13 = 0x10000000;
      if ( (unsigned int)SdbpOpenLocalDatabaseEx((_DWORD)inited, (unsigned int)v16, 268435458, 0, (__int64)&v13) )
      {
        v6 = inited[3];
        FirstGUIDIndexedTag = SdbFindFirstGUIDIndexedTag(v6, 28679, 36868, (_DWORD)a2, (__int64)v14);
        if ( FirstGUIDIndexedTag )
        {
          Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xD8u);
          v4 = Heap;
          if ( Heap )
          {
            *Heap = inited;
            Heap[1] = v6;
            *((_OWORD *)Heap + 3) = *a2;
            v9 = *a1;
            *((_DWORD *)Heap + 17) = FirstGUIDIndexedTag;
            *((_OWORD *)Heap + 2) = v9;
            *((_DWORD *)Heap + 6) = v12;
            if ( (unsigned int)SdbpReadApphelpBasicInfo(
                                 v6,
                                 FirstGUIDIndexedTag,
                                 (int)Heap + 72,
                                 (int)Heap + 76,
                                 (__int64)(Heap + 10),
                                 (__int64)Heap + 84) )
              return v4;
            LODWORD(v11) = FirstGUIDIndexedTag;
            AslLogCallPrintf(
              1,
              "SdbOpenApphelpInformation",
              2427,
              "Error reading apphelp basic information, apphelp may not be present for tagid 0x%lx",
              v11);
          }
          else
          {
            AslLogCallPrintf(1, "SdbOpenApphelpInformation", 2409, "Error allocating memory for apphelp info context");
          }
        }
      }
      else
      {
        AslLogCallPrintf(1, "SdbOpenApphelpInformation", 2382, "Failed to open database \"%ws\"", v16);
      }
    }
    SdbReleaseDatabase(inited);
    if ( v4 )
    {
      AslFree(NtCurrentPeb()->ProcessHeap, v4);
      return 0;
    }
  }
  else
  {
    AslLogCallPrintf(1, "SdbOpenApphelpInformation", 2360, "Failed to initialize database");
  }
  return v4;
}

```

## disassembly

```asm
0x180044140  mov     [rsp-8+arg_10], rbx
0x180044145  mov     [rsp-8+arg_18], rsi
0x18004414a  push    rbp
0x18004414b  push    rdi
0x18004414c  push    r12
0x18004414e  push    r14
0x180044150  push    r15
0x180044152  lea     rbp, [rsp-180h]
0x18004415a  sub     rsp, 280h
0x180044161  mov     rax, cs:__security_cookie
0x180044168  xor     rax, rsp
0x18004416b  mov     [rbp+1A0h+var_30], rax
0x180044172  xor     eax, eax
0x180044174  mov     [rsp+2A0h+var_270], 0
0x18004417c  xorps   xmm0, xmm0
0x18004417f  mov     [rsp+2A0h+var_248], rax
0x180044184  mov     r12, rdx
0x180044187  mov     r15, rcx
0x18004418a  xor     edx, edx
0x18004418c  mov     r8d, 14Ch
0x180044192  lea     ecx, [rax+4]
0x180044195  xor     ebx, ebx
0x180044197  movups  [rsp+2A0h+var_268], xmm0
0x18004419c  movups  [rsp+2A0h+var_258], xmm0
0x1800441a1  call    SdbInitDatabaseEx
0x1800441a6  mov     rdi, rax
0x1800441a9  test    rax, rax
0x1800441ac  jnz     short loc_1800441CF
0x1800441ae  lea     r9, aFailedToInitia_10; "Failed to initialize database"
0x1800441b5  mov     r8d, 938h
0x1800441bb  lea     rdx, aSdbopenapphelp_7; "SdbOpenApphelpInformation"
0x1800441c2  lea     ecx, [rbx+1]
0x1800441c5  call    AslLogCallPrintf
0x1800441ca  jmp     loc_180044361
0x1800441cf  lea     rax, [rsp+2A0h+var_240]
0x1800441d4  mov     dword ptr [rsp+2A0h+var_278], 104h
0x1800441dc  xor     r9d, r9d
0x1800441df  mov     [rsp+2A0h+var_280], rax
0x1800441e4  lea     r8, [rsp+2A0h+var_270]
0x1800441e9  mov     rdx, r15
0x1800441ec  mov     rcx, rdi
0x1800441ef  call    SdbResolveDatabaseEx
0x1800441f4  dec     eax
0x1800441f6  cmp     eax, 103h
0x1800441fb  ja      loc_18004431F
0x180044201  lea     rax, [rsp+2A0h+var_26C]
0x180044206  mov     [rsp+2A0h+var_26C], 10000000h
0x18004420e  xor     r9d, r9d
0x180044211  mov     [rsp+2A0h+var_280], rax
0x180044216  mov     r8d, 10000002h
0x18004421c  lea     rdx, [rsp+2A0h+var_240]
0x180044221  mov     rcx, rdi
0x180044224  call    SdbpOpenLocalDatabaseEx
0x180044229  test    eax, eax
0x18004422b  jnz     short loc_18004425A
0x18004422d  lea     rax, [rsp+2A0h+var_240]
0x180044232  mov     r8d, 94Eh
0x180044238  mov     [rsp+2A0h+var_280], rax
0x18004423d  lea     r9, aFailedToOpenDa_1; "Failed to open database \"%ws\""
0x180044244  lea     rdx, aSdbopenapphelp_7; "SdbOpenApphelpInformation"
0x18004424b  mov     ecx, 1
0x180044250  call    AslLogCallPrintf
0x180044255  jmp     loc_18004433D
0x18004425a  mov     r14, [rdi+18h]
0x18004425e  lea     rax, [rsp+2A0h+var_268]
0x180044263  mov     rcx, r14
0x180044266  mov     [rsp+2A0h+var_280], rax
0x18004426b  mov     edx, 7007h
0x180044270  mov     r8d, 9004h
0x180044276  mov     r9, r12
0x180044279  call    SdbFindFirstGUIDIndexedTag
0x18004427e  mov     esi, eax
0x180044280  test    eax, eax
0x180044282  jz      loc_18004433D
0x180044288  mov     rcx, gs:60h
0x180044291  mov     edx, 8; Flags
0x180044296  mov     r8d, 0D8h; Size
0x18004429c  mov     rcx, [rcx+30h]; HeapHandle
0x1800442a0  call    cs:__imp_RtlAllocateHeap
0x1800442a6  mov     rbx, rax
0x1800442a9  test    rax, rax
0x1800442ac  jnz     short loc_1800442BD
0x1800442ae  lea     r9, aErrorAllocatin_2; "Error allocating memory for apphelp inf"...
0x1800442b5  mov     r8d, 969h
0x1800442bb  jmp     short loc_18004432C
0x1800442bd  mov     [rax], rdi
0x1800442c0  lea     rdx, [rbx+50h]
0x1800442c4  mov     [rax+8], r14
0x1800442c8  lea     r9, [rbx+4Ch]
0x1800442cc  movups  xmm0, xmmword ptr [r12]
0x1800442d1  lea     r8, [rbx+48h]
0x1800442d5  mov     rcx, r14
0x1800442d8  movdqu  xmmword ptr [rax+30h], xmm0
0x1800442dd  movups  xmm1, xmmword ptr [r15]
0x1800442e1  mov     [rax+44h], esi
0x1800442e4  movdqu  xmmword ptr [rax+20h], xmm1
0x1800442e9  mov     eax, [rsp+2A0h+var_270]
0x1800442ed  mov     [rbx+18h], eax
0x1800442f0  lea     rax, [rbx+54h]
0x1800442f4  mov     [rsp+2A0h+var_278], rax
0x1800442f9  mov     [rsp+2A0h+var_280], rdx
0x1800442fe  mov     edx, esi
0x180044300  call    SdbpReadApphelpBasicInfo
0x180044305  test    eax, eax
0x180044307  jnz     short loc_180044361
0x180044309  mov     dword ptr [rsp+2A0h+var_280], esi
0x18004430d  lea     r9, aErrorReadingAp_0; "Error reading apphelp basic information"...
0x180044314  mov     r8d, 97Bh
0x18004431a  jmp     loc_180044244
0x18004431f  lea     r9, aFailedToResolv_4; "Failed to resolve database path"
0x180044326  mov     r8d, 945h
0x18004432c  lea     rdx, aSdbopenapphelp_7; "SdbOpenApphelpInformation"
0x180044333  mov     ecx, 1
0x180044338  call    AslLogCallPrintf
0x18004433d  mov     rcx, rdi; P
0x180044340  call    SdbReleaseDatabase
0x180044345  test    rbx, rbx
0x180044348  jz      short loc_180044361
0x18004434a  mov     rcx, gs:60h
0x180044353  mov     rdx, rbx
0x180044356  mov     rcx, [rcx+30h]
0x18004435a  call    AslFree
0x18004435f  xor     ebx, ebx
0x180044361  mov     rax, rbx
0x180044364  mov     rcx, [rbp+1A0h+var_30]
0x18004436b  xor     rcx, rsp; StackCookie
0x18004436e  call    __security_check_cookie
0x180044373  lea     r11, [rsp+2A0h+var_20]
0x18004437b  mov     rbx, [r11+40h]
0x18004437f  mov     rsi, [r11+48h]
0x180044383  mov     rsp, r11
0x180044386  pop     r15
0x180044388  pop     r14
0x18004438a  pop     r12
0x18004438c  pop     rdi
0x18004438d  pop     rbp
0x18004438e  retn
```
