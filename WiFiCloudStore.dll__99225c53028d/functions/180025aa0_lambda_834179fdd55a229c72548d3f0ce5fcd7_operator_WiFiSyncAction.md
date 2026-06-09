# _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(WiFiSyncAction)

- ea: `0x180025aa0`
- end: `0x180025b1a`
- name: `??R_lambda_834179fdd55a229c72548d3f0ce5fcd7_@@QEBA@W4WiFiSyncAction@@@Z`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180016ba4`
- `0x18002547c`

## callees

- `0x18000766c`
- `0x180025aa0`

## string_xrefs

- `0x180025aef`: `Profile name: %ws, Generation: %d, Local version: %llu, Cloud version: %llu, Local modified time: %llu, Cloud modified time: %llu, Attempting action: %u, Retry count: %lu`

## pseudocode

```c
void __fastcall _lambda_834179fdd55a229c72548d3f0ce5fcd7_::operator()(__int64 a1, int a2)
{
  _QWORD *v2; // r8
  int v4; // [rsp+48h] [rbp-10h]

  v2 = *(_QWORD **)(a1 + 8);
  if ( v2[3] > 7u )
    v2 = (_QWORD *)*v2;
  v4 = **(_DWORD **)(a1 + 56);
  wil::ActivityThreadWatcher::SetMessage(
    *(wil::ActivityThreadWatcher **)a1,
    "Profile name: %ws, Generation: %d, Local version: %llu, Cloud version: %llu, Local modified time: %llu, Cloud modifi"
    "ed time: %llu, Attempting action: %u, Retry count: %lu",
    v2,
    *(unsigned int *)(*(_QWORD *)(a1 + 16) + 44LL),
    **(_QWORD **)(a1 + 24),
    **(_QWORD **)(a1 + 32),
    **(_QWORD **)(a1 + 40),
    **(_QWORD **)(a1 + 48),
    a2,
    v4);
}

```

## disassembly

```asm
0x180025aa0  mov     [rsp+arg_0], rbx
0x180025aa5  push    rdi
0x180025aa6  sub     rsp, 50h
0x180025aaa  mov     rax, [rcx+38h]
0x180025aae  mov     r8, [rcx+8]
0x180025ab2  mov     r9d, [rax]
0x180025ab5  cmp     qword ptr [r8+18h], 7
0x180025aba  mov     rax, [rcx+30h]
0x180025abe  mov     r10, [rax]
0x180025ac1  mov     rax, [rcx+28h]
0x180025ac5  mov     r11, [rax]
0x180025ac8  mov     rax, [rcx+20h]
0x180025acc  mov     rbx, [rax]
0x180025acf  mov     rax, [rcx+18h]
0x180025ad3  mov     rdi, [rax]
0x180025ad6  mov     rax, [rcx+10h]
0x180025ada  jbe     short loc_180025ADF
0x180025adc  mov     r8, [r8]
0x180025adf  mov     rcx, [rcx]; this
0x180025ae2  mov     [rsp+58h+var_10], r9d
0x180025ae7  mov     r9d, [rax+2Ch]
0x180025aeb  mov     [rsp+58h+var_18], edx
0x180025aef  lea     rdx, aProfileNameWsG; "Profile name: %ws, Generation: %d, Loca"...
0x180025af6  mov     [rsp+58h+var_20], r10
0x180025afb  mov     [rsp+58h+var_28], r11
0x180025b00  mov     [rsp+58h+var_30], rbx
0x180025b05  mov     [rsp+58h+var_38], rdi
0x180025b0a  call    ?SetMessage@ActivityThreadWatcher@wil@@QEAAXPEBDZZ; wil::ActivityThreadWatcher::SetMessage(char const *,...)
0x180025b0f  mov     rbx, [rsp+58h+arg_0]
0x180025b14  add     rsp, 50h
0x180025b18  pop     rdi
0x180025b19  retn
```
