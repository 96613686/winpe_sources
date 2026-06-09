# CommonUtil::NewVSprintfW(ushort * *,ushort const *,char *)

- ea: `0x14000de68`
- end: `0x14000decf`
- name: `?NewVSprintfW@CommonUtil@@YAJPEAPEAGPEBGPEAD@Z`
- size: `103`
- prototype: `__int64 __fastcall(CommonUtil *this, unsigned __int16 **, char *, char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14000de38`

## callees

- `0x140001614`
- `0x14000dc20`
- `0x14000de68`

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
0x14000de68  mov     rax, rsp
0x14000de6b  mov     [rax+10h], rbx
0x14000de6f  push    rdi
0x14000de70  sub     rsp, 30h
0x14000de74  mov     r9, r8
0x14000de77  mov     qword ptr [rcx], 0
0x14000de7e  mov     r8, rdx
0x14000de81  mov     qword ptr [rax+8], 0
0x14000de89  mov     rdi, rcx
0x14000de8c  mov     qword ptr [rax+20h], 0
0x14000de94  lea     rdx, [rax+8]
0x14000de98  lea     rcx, [rax+20h]
0x14000de9c  call    ?DoFormating@?$CSprintfAlloc@U?$CNewSprintfPolicy@G@CommonUtil@@$0BAE@@CommonUtil@@SAJPEA_KPEAPEAGPEBGPEAD_K@Z; CommonUtil::CSprintfAlloc<CommonUtil::CNewSprintfPolicy<ushort>,260>::DoFormating(unsigned __int64 *,ushort * *,ushort const *,char *,unsigned __int64)
0x14000dea1  mov     ebx, eax
0x14000dea3  test    eax, eax
0x14000dea5  jns     short loc_14000DEBA
0x14000dea7  mov     rcx, [rsp+38h+arg_0]; void *
0x14000deac  test    rcx, rcx
0x14000deaf  jz      short loc_14000DEB6
0x14000deb1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000deb6  mov     eax, ebx
0x14000deb8  jmp     short loc_14000DEC4
0x14000deba  mov     rax, [rsp+38h+arg_0]
0x14000debf  mov     [rdi], rax
0x14000dec2  xor     eax, eax
0x14000dec4  mov     rbx, [rsp+38h+arg_8]
0x14000dec9  add     rsp, 30h
0x14000decd  pop     rdi
0x14000dece  retn
```
