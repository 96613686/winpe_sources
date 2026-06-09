# Microsoft::ISRC::CompletionTrieBuilder<std::pair<uint,uint>>::CompletionTrieBuilder<std::pair<uint,uint>>(void)

- ea: `0x18005c38c`
- end: `0x18005c485`
- name: `??0?$CompletionTrieBuilder@U?$pair@II@std@@@ISRC@Microsoft@@QEAA@XZ`
- size: `249`
- prototype: ``
- caller_count: `10`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180062904`
- `0x1800637c0`
- `0x180063e10`
- `0x180064800`
- `0x180064b88`
- `0x180064fa4`
- `0x180065520`
- `0x18006a9a8`
- `0x18006b2d8`
- `0x180076b38`

## callees

- `0x180004a04`
- `0x1800062a0`
- `0x180009f40`
- `0x180016e84`
- `0x180018980`
- `0x18005c38c`

## import_xrefs

- `api-ms-win-core-synch-ansi-l1-1-0!OpenMutexA` at `0x18005c469`
- `api-ms-win-core-synch-ansi-l1-1-0!OpenMutexA` at `0x18005c469`

## string_xrefs

- `0x18005c45b`: `CompletionTrieBuilder.Write`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Microsoft::ISRC::CompletionTrieBuilder<std::pair<unsigned int,unsigned int>>::CompletionTrieBuilder<std::pair<unsigned int,unsigned int>>(
        _QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  __int64 *v4; // rax
  __int64 v5; // rdx
  _DWORD *v6; // rax
  __int64 v7; // rdx
  __int64 *v8; // rax
  __int64 v10; // [rsp+20h] [rbp-28h] BYREF
  _QWORD *v11; // [rsp+28h] [rbp-20h]
  _QWORD *v12; // [rsp+30h] [rbp-18h]

  v12 = a1;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(a1);
  std::string::string(v2 + 24);
  v11 = a1 + 7;
  std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(a1 + 7);
  v10 = 1024;
  if ( (unsigned __int64)((__int64)(a1[9] - a1[7]) >> 3) < 0x400 )
    std::vector<Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::BuildNode *,std::allocator<Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::BuildNode *>>::_Reallocate<0>(
      a1 + 7,
      &v10);
  v3 = a1[8];
  if ( a1[7] == v3 )
  {
    v6 = operator new(0x40u);
    v11 = v6;
    *(_BYTE *)v6 = 0;
    v6[2] = 0;
    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v6 + 4);
    std::vector<std::pair<unsigned short,unsigned short>>::vector<std::pair<unsigned short,unsigned short>>(v7 + 40);
  }
  else
  {
    v4 = (__int64 *)(v3 - 8);
    v5 = *v4;
    a1[8] = v4;
    *(_BYTE *)v5 = 0;
    *(_DWORD *)(v5 + 8) = 0;
  }
  v10 = v5;
  v8 = (__int64 *)a1[1];
  if ( v8 == (__int64 *)a1[2] )
  {
    std::vector<Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode *,std::allocator<Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode *>>::_Emplace_reallocate<Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode *>(
      a1,
      a1[1],
      &v10);
  }
  else
  {
    *v8 = v5;
    a1[1] += 8LL;
  }
  a1[10] = OpenMutexA(0x100000u, 0, "CompletionTrieBuilder.Write");
  a1[11] = 0;
  return a1;
}

```

## disassembly

```asm
0x18005c38c  mov     [rsp+arg_8], rbx
0x18005c391  push    rdi
0x18005c392  sub     rsp, 40h
0x18005c396  mov     rbx, rcx
0x18005c399  mov     [rsp+48h+var_18], rcx
0x18005c39e  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18005c3a3  nop
0x18005c3a4  add     rcx, 18h
0x18005c3a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18005c3ad  nop
0x18005c3ae  lea     rdi, [rbx+38h]
0x18005c3b2  mov     [rsp+48h+var_20], rdi
0x18005c3b7  mov     rcx, rdi
0x18005c3ba  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18005c3bf  nop
0x18005c3c0  mov     ecx, 400h
0x18005c3c5  mov     [rsp+48h+var_28], rcx
0x18005c3ca  mov     rax, [rdi+10h]
0x18005c3ce  sub     rax, [rdi]
0x18005c3d1  sar     rax, 3
0x18005c3d5  cmp     rax, rcx
0x18005c3d8  jnb     short loc_18005C3E8
0x18005c3da  lea     rdx, [rsp+48h+var_28]
0x18005c3df  mov     rcx, rdi
0x18005c3e2  call    ??$_Reallocate@$0A@@?$vector@PEAUBuildNode@?$CompletionTrieBuilder@UVoid@ISRC@Microsoft@@@ISRC@Microsoft@@V?$allocator@PEAUBuildNode@?$CompletionTrieBuilder@UVoid@ISRC@Microsoft@@@ISRC@Microsoft@@@std@@@std@@AEAAXAEA_K@Z; std::vector<Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::BuildNode *,std::allocator<Microsoft::ISRC::CompletionTrieBuilder<Microsoft::ISRC::Void>::BuildNode *>>::_Reallocate<0>(unsigned __int64 &)
0x18005c3e7  nop
0x18005c3e8  mov     rax, [rdi+8]
0x18005c3ec  cmp     [rdi], rax
0x18005c3ef  jz      short loc_18005C406
0x18005c3f1  add     rax, 0FFFFFFFFFFFFFFF8h
0x18005c3f5  mov     rdx, [rax]
0x18005c3f8  mov     [rdi+8], rax
0x18005c3fc  xor     edi, edi
0x18005c3fe  mov     [rdx], dil
0x18005c401  mov     [rdx+8], edi
0x18005c404  jmp     short loc_18005C432
0x18005c406  mov     ecx, 40h ; '@'; Size
0x18005c40b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005c410  mov     rdx, rax
0x18005c413  mov     [rsp+48h+var_20], rax
0x18005c418  xor     edi, edi
0x18005c41a  mov     [rax], dil
0x18005c41d  mov     [rax+8], edi
0x18005c420  lea     rcx, [rax+10h]
0x18005c424  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18005c429  lea     rcx, [rdx+28h]
0x18005c42d  call    ??0?$vector@U?$pair@GG@std@@V?$allocator@U?$pair@GG@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<ushort,ushort>>::vector<std::pair<ushort,ushort>>(void)
0x18005c432  mov     [rsp+48h+var_28], rdx
0x18005c437  mov     rax, [rbx+8]
0x18005c43b  cmp     rax, [rbx+10h]
0x18005c43f  jz      short loc_18005C44B
0x18005c441  mov     [rax], rdx
0x18005c444  add     qword ptr [rbx+8], 8
0x18005c449  jmp     short loc_18005C45B
0x18005c44b  lea     r8, [rsp+48h+var_28]
0x18005c450  mov     rdx, rax
0x18005c453  mov     rcx, rbx
0x18005c456  call    ??$_Emplace_reallocate@PEAUBuildNode@?$CompletionTrieBuilder@_K@ISRC@Microsoft@@@?$vector@PEAUBuildNode@?$CompletionTrieBuilder@_K@ISRC@Microsoft@@V?$allocator@PEAUBuildNode@?$CompletionTrieBuilder@_K@ISRC@Microsoft@@@std@@@std@@AEAAPEAPEAUBuildNode@?$CompletionTrieBuilder@_K@ISRC@Microsoft@@QEAPEAU2345@$$QEAPEAU2345@@Z; std::vector<Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode *,std::allocator<Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode *>>::_Emplace_reallocate<Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode *>(Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode * * const,Microsoft::ISRC::CompletionTrieBuilder<unsigned __int64>::BuildNode * &&)
0x18005c45b  lea     r8, Name; "CompletionTrieBuilder.Write"
0x18005c462  xor     edx, edx; bInheritHandle
0x18005c464  mov     ecx, 100000h; dwDesiredAccess
0x18005c469  call    cs:__imp_OpenMutexA
0x18005c46f  mov     [rbx+50h], rax
0x18005c473  mov     [rbx+58h], rdi
0x18005c477  mov     rax, rbx
0x18005c47a  mov     rbx, [rsp+48h+arg_8]
0x18005c47f  add     rsp, 40h
0x18005c483  pop     rdi
0x18005c484  retn
```
