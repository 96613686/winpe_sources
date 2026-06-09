# common_flush_all(bool)

- ea: `0x412521`
- end: `0x41256e`
- name: `?common_flush_all@@YAH_N@Z`
- size: `77`
- prototype: `int __cdecl(bool)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x41262b`
- `0x412673`

## callees

- `0x412475`
- `0x412521`

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
0x412521  mov     edi, edi
0x412523  push    ebp
0x412524  mov     ebp, esp
0x412526  sub     esp, 20h
0x412529  and     [ebp+var_8], 0
0x41252d  lea     eax, [ebp+var_8]
0x412530  and     [ebp+var_C], 0
0x412534  lea     ecx, [ebp+var_1]
0x412537  mov     [ebp+var_20], eax
0x41253a  lea     eax, [ebp+arg_0]
0x41253d  mov     [ebp+var_1C], eax
0x412540  lea     eax, [ebp+var_C]
0x412543  push    8
0x412545  mov     [ebp+var_18], eax
0x412548  pop     eax
0x412549  mov     [ebp+var_10], eax
0x41254c  mov     [ebp+var_14], eax
0x41254f  lea     eax, [ebp+var_10]
0x412552  push    eax
0x412553  lea     eax, [ebp+var_20]
0x412556  push    eax
0x412557  lea     eax, [ebp+var_14]
0x41255a  push    eax
0x41255b  call    ??$?RV_lambda_2cc53f568c5a2bb6f192f930a45d44ea_@@AAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@V_lambda_c2ffc0b7726aa6be21d5f0026187e748_@@@?$__crt_seh_guarded_call@X@@QAEX$$QAV_lambda_2cc53f568c5a2bb6f192f930a45d44ea_@@AAV_lambda_ab61a845afdef5b7c387490eaf3616ee_@@$$QAV_lambda_c2ffc0b7726aa6be21d5f0026187e748_@@@Z
0x412560  cmp     [ebp+arg_0], 0
0x412564  mov     eax, [ebp+var_8]
0x412567  jnz     short locret_41256C
0x412569  mov     eax, [ebp+var_C]
0x41256c  leave
0x41256d  retn
```
