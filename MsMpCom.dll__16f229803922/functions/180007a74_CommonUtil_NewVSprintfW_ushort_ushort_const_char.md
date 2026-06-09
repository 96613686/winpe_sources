# CommonUtil::NewVSprintfW(ushort * *,ushort const *,char *)

- ea: `0x180007a74`
- end: `0x180007adc`
- name: `?NewVSprintfW@CommonUtil@@YAJPEAPEAGPEBGPEAD@Z`
- size: `104`
- prototype: `__int64 __fastcall(CommonUtil *__hidden this, unsigned __int16 **, const unsigned __int16 *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180007a44`

## callees

- `0x180007858`
- `0x180007a74`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180007abd`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180007abd`

## pseudocode

```c
__int64 __fastcall CommonUtil::NewVSprintfW(
        CommonUtil *this,
        unsigned __int16 **a2,
        const unsigned __int16 *a3,
        char *a4)
{
  int v5; // ebx
  void *v7; // [rsp+40h] [rbp+8h] BYREF
  unsigned __int64 v8; // [rsp+58h] [rbp+20h] BYREF

  *(_QWORD *)this = 0;
  v7 = 0;
  v8 = 0;
  v5 = CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<unsigned short>,260>::DoFormating(
         &v8,
         &v7,
         (__int64)a2,
         (__int64)a3);
  if ( v5 >= 0 )
  {
    *(_QWORD *)this = v7;
    return 0;
  }
  else
  {
    if ( v7 )
      operator delete[](v7);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x180007a74  mov     rax, rsp
0x180007a77  mov     [rax+10h], rbx
0x180007a7b  push    rdi
0x180007a7c  sub     rsp, 30h
0x180007a80  mov     r9, r8
0x180007a83  mov     qword ptr [rcx], 0
0x180007a8a  mov     r8, rdx
0x180007a8d  mov     qword ptr [rax+8], 0
0x180007a95  mov     rdi, rcx
0x180007a98  mov     qword ptr [rax+20h], 0
0x180007aa0  lea     rdx, [rax+8]
0x180007aa4  lea     rcx, [rax+20h]
0x180007aa8  call    ?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@G@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEAGPEBGPEAD_K@Z; CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<ushort>,260>::DoFormating(unsigned __int64 *,ushort * *,ushort const *,char *,unsigned __int64)
0x180007aad  mov     ebx, eax
0x180007aaf  test    eax, eax
0x180007ab1  jns     short loc_180007AC7
0x180007ab3  mov     rcx, [rsp+38h+arg_0]
0x180007ab8  test    rcx, rcx
0x180007abb  jz      short loc_180007AC3
0x180007abd  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180007ac3  mov     eax, ebx
0x180007ac5  jmp     short loc_180007AD1
0x180007ac7  mov     rax, [rsp+38h+arg_0]
0x180007acc  mov     [rdi], rax
0x180007acf  xor     eax, eax
0x180007ad1  mov     rbx, [rsp+38h+arg_8]
0x180007ad6  add     rsp, 30h
0x180007ada  pop     rdi
0x180007adb  retn
```
