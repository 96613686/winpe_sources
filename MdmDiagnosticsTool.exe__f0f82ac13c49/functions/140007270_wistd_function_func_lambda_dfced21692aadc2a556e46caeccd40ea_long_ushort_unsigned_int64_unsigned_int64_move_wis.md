# wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::__move(wistd::__function::__base<long (ushort *,unsigned __int64,unsigned __int64 *)> *)

- ea: `0x140007270`
- end: `0x140007283`
- name: `?__move@?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAXPEAV?$__base@$$A6AJPEAG_KPEA_K@Z@23@@Z`
- size: `19`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::__move(
        __int64 a1,
        _QWORD *a2)
{
  __int64 result; // rax

  *a2 = &wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  result = *(_QWORD *)(a1 + 8);
  a2[1] = result;
  return result;
}

```

## disassembly

```asm
0x140007270  lea     rax, ??_7?$__func@V_lambda_dfced21692aadc2a556e46caeccd40ea_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_dfced21692aadc2a556e46caeccd40ea_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x140007277  mov     [rdx], rax
0x14000727a  mov     rax, [rcx+8]
0x14000727e  mov     [rdx+8], rax
0x140007282  retn
```
