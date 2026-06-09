# CommonUtil::UtilRegGetValueString(HKEY__ *,ushort const *,ushort * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)

- ea: `0x14000fb20`
- end: `0x14000fb98`
- name: `?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEBGPEAPEAGW4UTIL_REG_EXPAND_STRING@1@PEAK@Z`
- size: `120`
- prototype: `__int64 __fastcall(CommonUtil *, HKEY, unsigned __int16 *, __int64, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140002c18`
- `0x140003e58`

## callees

- `0x1400015f4`
- `0x14000f8f0`
- `0x14000fb20`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilRegGetValueString(
        CommonUtil *a1,
        HKEY a2,
        unsigned __int16 *a3,
        __int64 a4,
        void *a5)
{
  unsigned __int64 v6; // rdx
  int ValueAlloc; // ebx
  unsigned __int8 **v9; // [rsp+30h] [rbp-28h]
  unsigned __int64 v10; // [rsp+38h] [rbp-20h]
  unsigned int v11[6]; // [rsp+40h] [rbp-18h] BYREF
  int v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  *(_QWORD *)v11 = 0;
  a5 = 0;
  ValueAlloc = CommonUtil::UtilRegGetValueAlloc(a1, a2, a3, (unsigned int)&v12, v11, (unsigned __int64 *)&a5, v9, v10);
  if ( ValueAlloc >= 0 )
  {
    *(_QWORD *)a3 = a5;
    return 0;
  }
  else
  {
    if ( a5 )
      operator delete(a5, v6);
    return (unsigned int)ValueAlloc;
  }
}

```

## disassembly

```asm
0x14000fb20  mov     r11, rsp
0x14000fb23  mov     [r11+8], rbx
0x14000fb27  mov     [r11+20h], r9d
0x14000fb2b  push    rdi
0x14000fb2c  sub     rsp, 50h
0x14000fb30  lea     rax, [r11+28h]
0x14000fb34  mov     [rsp+58h+arg_18], 0
0x14000fb3c  mov     [r11-30h], rax
0x14000fb40  lea     r9, [r11+20h]; unsigned int
0x14000fb44  lea     rax, [r11-18h]
0x14000fb48  mov     qword ptr [r11-18h], 0
0x14000fb50  mov     [r11-38h], rax
0x14000fb54  mov     rdi, r8
0x14000fb57  mov     qword ptr [r11+28h], 0
0x14000fb5f  call    ?UtilRegGetValueAlloc@CommonUtil@@YAJPEAUHKEY__@@PEBGKPEAKPEA_KPEAPEAE_K@Z; CommonUtil::UtilRegGetValueAlloc(HKEY__ *,ushort const *,ulong,ulong *,unsigned __int64 *,uchar * *,unsigned __int64)
0x14000fb64  mov     ebx, eax
0x14000fb66  test    eax, eax
0x14000fb68  jns     short loc_14000FB80
0x14000fb6a  mov     rcx, [rsp+58h+arg_20]; void *
0x14000fb72  test    rcx, rcx
0x14000fb75  jz      short loc_14000FB7C
0x14000fb77  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000fb7c  mov     eax, ebx
0x14000fb7e  jmp     short loc_14000FB8D
0x14000fb80  mov     rax, [rsp+58h+arg_20]
0x14000fb88  mov     [rdi], rax
0x14000fb8b  xor     eax, eax
0x14000fb8d  mov     rbx, [rsp+58h+arg_0]
0x14000fb92  add     rsp, 50h
0x14000fb96  pop     rdi
0x14000fb97  retn
```
