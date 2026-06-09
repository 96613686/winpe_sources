# wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (ushort *,unsigned __int64,unsigned __int64 *)>::__move(wistd::__function::__base<long (ushort *,unsigned __int64,unsigned __int64 *)> *)

- ea: `0x14000d680`
- end: `0x14000d694`
- name: `?__move@?$__func@V_lambda_843902387d8c5b5ae08b6cfe18992148_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAXPEAV?$__base@$$A6AJPEAG_KPEA_K@Z@23@@Z`
- size: `20`
- prototype: `void **__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void **__fastcall wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::__move(
        __int64 a1,
        __int64 a2)
{
  void **result; // rax

  result = &wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  *(_QWORD *)a2 = &wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  *(_OWORD *)(a2 + 8) = *(_OWORD *)(a1 + 8);
  return result;
}

```

## disassembly

```asm
0x14000d680  lea     rax, ??_7?$__func@V_lambda_843902387d8c5b5ae08b6cfe18992148_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x14000d687  mov     [rdx], rax
0x14000d68a  movups  xmm0, xmmword ptr [rcx+8]
0x14000d68e  movdqu  xmmword ptr [rdx+8], xmm0
0x14000d693  retn
```
