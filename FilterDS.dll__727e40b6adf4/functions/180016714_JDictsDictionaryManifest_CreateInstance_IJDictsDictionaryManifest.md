# JDictsDictionaryManifest::CreateInstance(IJDictsDictionaryManifest * *)

- ea: `0x180016714`
- end: `0x18001679b`
- name: `?CreateInstance@JDictsDictionaryManifest@@SAJPEAPEAUIJDictsDictionaryManifest@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct IJDictsDictionaryManifest **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f1d8`

## callees

- `0x180001a30`
- `0x180016714`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall JDictsDictionaryManifest::CreateInstance(struct IJDictsDictionaryManifest **a1)
{
  _DWORD *v2; // rax
  const char *v3; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a1 = 0;
  try
  {
    v2 = operator new(0x68u);
    if ( v2 )
    {
      *(_QWORD *)v2 = &JDictsDictionaryManifest::`vftable';
      v2[2] = 0;
      *((_QWORD *)v2 + 2) = 0;
      *((_QWORD *)v2 + 3) = 0;
      *((_QWORD *)v2 + 7) = 7;
      *((_QWORD *)v2 + 6) = 0;
      *((_WORD *)v2 + 16) = 0;
      *((_QWORD *)v2 + 11) = 7;
      *((_QWORD *)v2 + 10) = 0;
      *((_WORD *)v2 + 32) = 0;
      v2[24] = 0;
    }
    *a1 = (struct IJDictsDictionaryManifest *)v2;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 8LL))(v2);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2C,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdi"
                                         "ctsdictionarymanifest.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x180016714  push    rbx
0x180016716  sub     rsp, 20h
0x18001671a  mov     rbx, rcx
0x18001671d  mov     qword ptr [rcx], 0
0x180016724  mov     ecx, 68h ; 'h'; Size
0x180016729  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001672e  mov     rcx, rax
0x180016731  test    rcx, rcx
0x180016734  jz      short loc_18001677D
0x180016736  lea     rax, ??_7JDictsDictionaryManifest@@6B@; const JDictsDictionaryManifest::`vftable'
0x18001673d  mov     [rcx], rax
0x180016740  mov     dword ptr [rcx+8], 0
0x180016747  mov     qword ptr [rcx+10h], 0
0x18001674f  mov     qword ptr [rcx+18h], 0
0x180016757  mov     edx, 7
0x18001675c  mov     [rcx+38h], rdx
0x180016760  mov     qword ptr [rcx+30h], 0
0x180016768  xor     eax, eax
0x18001676a  mov     [rcx+20h], ax
0x18001676e  mov     [rcx+58h], rdx
0x180016772  mov     [rcx+50h], rax
0x180016776  mov     [rcx+40h], ax
0x18001677a  mov     [rcx+60h], eax
0x18001677d  mov     [rbx], rcx
0x180016780  mov     rax, [rcx]
0x180016783  mov     rax, [rax+8]
0x180016787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001678c  xor     eax, eax
0x18001678e  jmp     short loc_180016794
0x180016790  mov     eax, [rsp+28h+arg_0]
0x180016794  add     rsp, 20h
0x180016798  pop     rbx
0x180016799  retn
```
