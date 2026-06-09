# std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(char const (&)[25],char const (&)[15])

- ea: `0x18000b358`
- end: `0x18000b3c4`
- name: `??$?0AEAY0BJ@$$CBDAEAY0P@$$CBD$0A@@?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@AEAY0BJ@$$CBDAEAY0P@$$CBD@Z`
- size: `108`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b308`

## callees

- `0x180026bc8`

## string_xrefs

- `0x18000b3ae`: `LastWriterWins`

## pseudocode

```c
__int64 __fastcall std::pair<std::string,std::string>::pair<std::string,std::string>(__int64 a1)
{
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::string::_Construct<1,char const *>(a1, "CloudData.ConflictPolicy", 24);
  *(_OWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  std::string::_Construct<1,char const *>(a1 + 32, "LastWriterWins", 14);
  return a1;
}

```

## disassembly

```asm
0x18000b358  mov     [rsp+arg_0], rcx
0x18000b35d  push    rbx
0x18000b35e  sub     rsp, 20h
0x18000b362  mov     rbx, rcx
0x18000b365  xorps   xmm0, xmm0
0x18000b368  movups  xmmword ptr [rcx], xmm0
0x18000b36b  mov     qword ptr [rcx+10h], 0
0x18000b373  mov     qword ptr [rcx+18h], 0
0x18000b37b  mov     r8d, 18h
0x18000b381  lea     rdx, aClouddataConfl; "CloudData.ConflictPolicy"
0x18000b388  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000b38d  nop
0x18000b38e  lea     rcx, [rbx+20h]
0x18000b392  xorps   xmm0, xmm0
0x18000b395  movups  xmmword ptr [rcx], xmm0
0x18000b398  mov     qword ptr [rcx+10h], 0
0x18000b3a0  mov     qword ptr [rcx+18h], 0
0x18000b3a8  mov     r8d, 0Eh
0x18000b3ae  lea     rdx, aLastwriterwins; "LastWriterWins"
0x18000b3b5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000b3ba  nop
0x18000b3bb  mov     rax, rbx
0x18000b3be  add     rsp, 20h
0x18000b3c2  pop     rbx
0x18000b3c3  retn
```
