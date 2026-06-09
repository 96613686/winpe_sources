# wil::unique_any_array_ptr<tagSemanticVector,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,SemanticVectorDeleter,unsigned __int64>::reset(void)

- ea: `0x1400469a4`
- end: `0x140046a17`
- name: `?reset@?$unique_any_array_ptr@UtagSemanticVector@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@USemanticVectorDeleter@@_K@wil@@QEAAXXZ`
- size: `115`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140046734`
- `0x140046770`
- `0x1400476f0`
- `0x1400478a4`

## callees

- `0x14004433c`
- `0x1400469a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400469f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400469f2`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<tagSemanticVector,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,SemanticVectorDeleter,unsigned __int64>::reset(
        __int64 a1)
{
  _OWORD *v1; // rdi
  _OWORD *v3; // rsi
  __int128 v4; // xmm1
  _OWORD v5[2]; // [rsp+20h] [rbp-28h] BYREF

  v1 = *(_OWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[2 * *(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
    {
      v4 = v1[1];
      v5[0] = *v1;
      v5[1] = v4;
      FreeSemanticVector((struct tagSemanticVector *)v5);
      v1 += 2;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1400469a4  mov     [rsp+arg_0], rbx
0x1400469a9  mov     [rsp+arg_8], rsi
0x1400469ae  push    rdi
0x1400469af  sub     rsp, 40h
0x1400469b3  mov     rdi, [rcx]
0x1400469b6  mov     rbx, rcx
0x1400469b9  test    rdi, rdi
0x1400469bc  jz      short loc_140046A07
0x1400469be  mov     rsi, [rcx+8]
0x1400469c2  shl     rsi, 5
0x1400469c6  add     rsi, rdi
0x1400469c9  jmp     short loc_1400469EA
0x1400469cb  movups  xmm0, xmmword ptr [rdi]
0x1400469ce  lea     rcx, [rsp+48h+var_28]; struct tagSemanticVector *
0x1400469d3  movups  xmm1, xmmword ptr [rdi+10h]
0x1400469d7  movaps  [rsp+48h+var_28], xmm0
0x1400469dc  movaps  [rsp+48h+var_18], xmm1
0x1400469e1  call    ?FreeSemanticVector@@YAXPEAUtagSemanticVector@@@Z; FreeSemanticVector(tagSemanticVector *)
0x1400469e6  add     rdi, 20h ; ' '
0x1400469ea  cmp     rdi, rsi
0x1400469ed  jnz     short loc_1400469CB
0x1400469ef  mov     rcx, [rbx]; pv
0x1400469f2  call    cs:__imp_CoTaskMemFree
0x1400469f8  mov     qword ptr [rbx], 0
0x1400469ff  mov     qword ptr [rbx+8], 0
0x140046a07  mov     rbx, [rsp+48h+arg_0]
0x140046a0c  mov     rsi, [rsp+48h+arg_8]
0x140046a11  add     rsp, 40h
0x140046a15  pop     rdi
0x140046a16  retn
```
