# common_flush_all(bool)

- ea: `0x411c29`
- end: `0x411c76`
- name: `?common_flush_all@@YAH_N@Z`
- size: `77`
- prototype: `int __cdecl(bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x411d33`
- `0x411d7b`

## callees

- `0x411b7d`
- `0x411c29`

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
0x411c29  mov     edi, edi
0x411c2b  push    ebp
0x411c2c  mov     ebp, esp
0x411c2e  sub     esp, 20h
0x411c31  and     [ebp+var_8], 0
0x411c35  lea     eax, [ebp+var_8]
0x411c38  and     [ebp+var_C], 0
0x411c3c  lea     ecx, [ebp+var_1]
0x411c3f  mov     [ebp+var_20], eax
0x411c42  lea     eax, [ebp+arg_0]
0x411c45  mov     [ebp+var_1C], eax
0x411c48  lea     eax, [ebp+var_C]
0x411c4b  push    8
0x411c4d  mov     [ebp+var_18], eax
0x411c50  pop     eax
0x411c51  mov     [ebp+var_10], eax
0x411c54  mov     [ebp+var_14], eax
0x411c57  lea     eax, [ebp+var_10]
0x411c5a  push    eax
0x411c5b  lea     eax, [ebp+var_20]
0x411c5e  push    eax
0x411c5f  lea     eax, [ebp+var_14]
0x411c62  push    eax
0x411c63  call    ??$?RV_lambda_2cc53f568c5a2bb6f192f930a45d44ea_@@AAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@V_lambda_c2ffc0b7726aa6be21d5f0026187e748_@@@?$__crt_seh_guarded_call@X@@QAEX$$QAV_lambda_2cc53f568c5a2bb6f192f930a45d44ea_@@AAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@$$QAV_lambda_c2ffc0b7726aa6be21d5f0026187e748_@@@Z
0x411c68  cmp     [ebp+arg_0], 0
0x411c6c  mov     eax, [ebp+var_8]
0x411c6f  jnz     short locret_411C74
0x411c71  mov     eax, [ebp+var_C]
0x411c74  leave
0x411c75  retn
```
