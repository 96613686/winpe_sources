# common_flush_all(bool)

- ea: `0x4159ab`
- end: `0x4159f8`
- name: `?common_flush_all@@YAH_N@Z`
- size: `77`
- prototype: `int __cdecl(bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x415ab5`
- `0x415afd`

## callees

- `0x4158ff`
- `0x4159ab`

## pseudocode

```c
int __cdecl common_flush_all(bool a1)
{
  int result; // eax
  _DWORD v2[3]; // [esp+0h] [ebp-20h] BYREF
  int v3; // [esp+Ch] [ebp-14h] BYREF
  int v4; // [esp+10h] [ebp-10h] BYREF
  int v5; // [esp+14h] [ebp-Ch] BYREF
  int v6; // [esp+18h] [ebp-8h] BYREF

  v6 = 0;
  v5 = 0;
  v2[0] = &v6;
  v2[1] = &a1;
  v2[2] = &v5;
  v4 = 8;
  v3 = 8;
  __crt_seh_guarded_call<void>::operator()<_lambda_2cc53f568c5a2bb6f192f930a45d44ea_,_lambda_ab61a845afdef5b7c387490eaf3616ee_ &,_lambda_c2ffc0b7726aa6be21d5f0026187e748_>(
    &v3,
    v2,
    &v4);
  result = v6;
  if ( !a1 )
    return v5;
  return result;
}

```

## disassembly

```asm
0x4159ab  mov     edi, edi
0x4159ad  push    ebp
0x4159ae  mov     ebp, esp
0x4159b0  sub     esp, 20h
0x4159b3  and     [ebp+var_8], 0
0x4159b7  lea     eax, [ebp+var_8]
0x4159ba  and     [ebp+var_C], 0
0x4159be  lea     ecx, [ebp+var_1]
0x4159c1  mov     [ebp+var_20], eax
0x4159c4  lea     eax, [ebp+arg_0]
0x4159c7  mov     [ebp+var_1C], eax
0x4159ca  lea     eax, [ebp+var_C]
0x4159cd  push    8
0x4159cf  mov     [ebp+var_18], eax
0x4159d2  pop     eax
0x4159d3  mov     [ebp+var_10], eax
0x4159d6  mov     [ebp+var_14], eax
0x4159d9  lea     eax, [ebp+var_10]
0x4159dc  push    eax
0x4159dd  lea     eax, [ebp+var_20]
0x4159e0  push    eax
0x4159e1  lea     eax, [ebp+var_14]
0x4159e4  push    eax
0x4159e5  call    ??$?RV_lambda_2cc53f568c5a2bb6f192f930a45d44ea_@@AAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@V_lambda_c2ffc0b7726aa6be21d5f0026187e748_@@@?$__crt_seh_guarded_call@X@@QAEX$$QAV_lambda_2cc53f568c5a2bb6f192f930a45d44ea_@@AAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@$$QAV_lambda_c2ffc0b7726aa6be21d5f0026187e748_@@@Z
0x4159ea  cmp     [ebp+arg_0], 0
0x4159ee  mov     eax, [ebp+var_8]
0x4159f1  jnz     short locret_4159F6
0x4159f3  mov     eax, [ebp+var_C]
0x4159f6  leave
0x4159f7  retn
```
