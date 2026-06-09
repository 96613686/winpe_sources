# MosQueryAnyPackagesFromPath(ushort const *,bool *,StackMode)

- ea: `0x18000aee0`
- end: `0x18000af4c`
- name: `?MosQueryAnyPackagesFromPath@@YAJPEBGPEA_NW4StackMode@@@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64, bool *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000ae68`
- `0x18000aee0`
- `0x18000b284`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000af1c`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000af1c`

## string_xrefs

- `0x18000af13`: `MosQueryAnyPackagesFromPath`

## pseudocode

```c
__int64 __fastcall MosQueryAnyPackagesFromPath(__int64 a1, bool *a2, unsigned int a3)
{
  bool *v3; // rdi
  unsigned int v4; // ebx
  int v5; // eax
  __int128 v7; // [rsp+20h] [rbp-28h] BYREF
  __int64 v8; // [rsp+30h] [rbp-18h]

  v3 = a2;
  v7 = 0;
  v4 = 0;
  v8 = 0;
  LOBYTE(a2) = 1;
  v5 = MosQueryPackagesFromPathInternal(a1, a2, &v7, a3);
  if ( v5 >= 0 )
    *v3 = (_QWORD)v7 != *((_QWORD *)&v7 + 1);
  else
    v4 = ZTraceReportPropagationNoThis(v5, "MosQueryAnyPackagesFromPath", 63);
  std::vector<unsigned int>::~vector<unsigned int>(&v7);
  return v4;
}

```

## disassembly

```asm
0x18000aee0  mov     rax, rsp
0x18000aee3  mov     [rax+8], rbx
0x18000aee7  push    rdi
0x18000aee8  sub     rsp, 40h
0x18000aeec  mov     rdi, rdx
0x18000aeef  xorps   xmm0, xmm0
0x18000aef2  movdqu  xmmword ptr [rax-28h], xmm0
0x18000aef7  xor     ebx, ebx
0x18000aef9  mov     [rax-18h], rbx
0x18000aefd  mov     r9d, r8d
0x18000af00  lea     r8, [rax-28h]
0x18000af04  mov     dl, 1
0x18000af06  call    MosQueryPackagesFromPathInternal
0x18000af0b  test    eax, eax
0x18000af0d  jns     short loc_18000AF26
0x18000af0f  lea     r8d, [rbx+3Fh]
0x18000af13  lea     rdx, aMosqueryanypac_0; "MosQueryAnyPackagesFromPath"
0x18000af1a  mov     ecx, eax
0x18000af1c  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000af22  mov     ebx, eax
0x18000af24  jmp     short loc_18000AF35
0x18000af26  mov     rax, [rsp+48h+var_20]
0x18000af2b  cmp     [rsp+48h+var_28], rax
0x18000af30  setnz   al
0x18000af33  mov     [rdi], al
0x18000af35  lea     rcx, [rsp+48h+var_28]
0x18000af3a  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x18000af3f  mov     eax, ebx
0x18000af41  mov     rbx, [rsp+48h+arg_0]
0x18000af46  add     rsp, 40h
0x18000af4a  pop     rdi
0x18000af4b  retn
```
