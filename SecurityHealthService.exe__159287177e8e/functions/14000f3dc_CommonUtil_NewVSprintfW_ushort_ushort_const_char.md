# CommonUtil::NewVSprintfW(ushort * *,ushort const *,char *)

- ea: `0x14000f3dc`
- end: `0x14000f443`
- name: `?NewVSprintfW@CommonUtil@@YAJPEAPEAGPEBGPEAD@Z`
- size: `103`
- prototype: `__int64 __fastcall(CommonUtil *this, unsigned __int16 **, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000f3ac`

## callees

- `0x1400015f4`
- `0x14000f194`
- `0x14000f3dc`

## pseudocode

```c
__int64 __fastcall CommonUtil::NewVSprintfW(CommonUtil *this, unsigned __int16 **a2, char *a3, char *a4)
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
         (const unsigned __int16 *)a2,
         a3);
  if ( v5 >= 0 )
  {
    *(_QWORD *)this = v7;
    return 0;
  }
  else
  {
    if ( v7 )
      operator delete(v7);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x14000f3dc  mov     rax, rsp
0x14000f3df  mov     [rax+10h], rbx
0x14000f3e3  push    rdi
0x14000f3e4  sub     rsp, 30h
0x14000f3e8  mov     r9, r8
0x14000f3eb  mov     qword ptr [rcx], 0
0x14000f3f2  mov     r8, rdx
0x14000f3f5  mov     qword ptr [rax+8], 0
0x14000f3fd  mov     rdi, rcx
0x14000f400  mov     qword ptr [rax+20h], 0
0x14000f408  lea     rdx, [rax+8]
0x14000f40c  lea     rcx, [rax+20h]
0x14000f410  call    ?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@G@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEAGPEBGPEAD_K@Z; CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<ushort>,260>::DoFormating(unsigned __int64 *,ushort * *,ushort const *,char *,unsigned __int64)
0x14000f415  mov     ebx, eax
0x14000f417  test    eax, eax
0x14000f419  jns     short loc_14000F42E
0x14000f41b  mov     rcx, [rsp+38h+arg_0]; void *
0x14000f420  test    rcx, rcx
0x14000f423  jz      short loc_14000F42A
0x14000f425  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f42a  mov     eax, ebx
0x14000f42c  jmp     short loc_14000F438
0x14000f42e  mov     rax, [rsp+38h+arg_0]
0x14000f433  mov     [rdi], rax
0x14000f436  xor     eax, eax
0x14000f438  mov     rbx, [rsp+38h+arg_8]
0x14000f43d  add     rsp, 30h
0x14000f441  pop     rdi
0x14000f442  retn
```
