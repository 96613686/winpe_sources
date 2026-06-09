# tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::serialize(tson::output_archive &,tip2::details::serialize_options)

- ea: `0x180024310`
- end: `0x1800243f5`
- name: `?serialize@?$merged_data@U_tip_A9InitialConfigurationTaskTipTest@@U1@@details@tip2@@EEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task`

## callees

- `0x180022cb8`
- `0x1800238d8`
- `0x180024310`
- `0x180024f48`

## string_xrefs

- `0x1800243b8`: `taskStatus`

## pseudocode

```c
void __fastcall tip2::details::merged_data<_tip_A9InitialConfigurationTaskTipTest,_tip_A9InitialConfigurationTaskTipTest>::serialize(
        __int64 a1,
        __int64 a2,
        char a3)
{
  _BYTE *v3; // rsi
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rax
  __int64 v9; // rdx

  v3 = (_BYTE *)(a2 + 8);
  if ( (a3 & 2) != 0 )
  {
    *v3 = 7;
    *(_QWORD *)a2 = "metrics";
    tson::output_archive::write_name((tson::output_archive *)a2, 0);
    v7 = *(_QWORD *)(a2 + 128);
    if ( v7 >= 0x19 )
    {
      *(_BYTE *)(a2 + 24) = 1;
    }
    else
    {
      *(_DWORD *)(a2 + 4 * v7 + 28) = 0;
      ++*(_QWORD *)(a2 + 128);
    }
    *(_DWORD *)(a1 + 184) = 0;
    tson::output_archive::finishNode((tson::output_archive *)a2);
  }
  if ( (a3 & 1) != 0 )
  {
    *v3 = 4;
    *(_QWORD *)a2 = "test";
    tson::output_archive::write_name((tson::output_archive *)a2, 0);
    v8 = *(_QWORD *)(a2 + 128);
    if ( v8 >= 0x19 )
    {
      *(_BYTE *)(a2 + 24) = 1;
    }
    else
    {
      *(_DWORD *)(a2 + 4 * v8 + 28) = 0;
      ++*(_QWORD *)(a2 + 128);
    }
    *v3 = 10;
    *(_QWORD *)a2 = "taskStatus";
    v9 = a1 + 272;
    if ( !a1 )
      v9 = 16;
    tson::output_archive::saveValue((tson::output_archive *)a2, *(_DWORD *)v9);
    tson::output_archive::finishNode((tson::output_archive *)a2);
  }
}

```

## disassembly

```asm
0x180024310  push    rbx
0x180024312  push    rbp
0x180024313  push    rsi
0x180024314  push    rdi
0x180024315  push    r14
0x180024317  sub     rsp, 20h
0x18002431b  lea     rsi, [rdx+8]
0x18002431f  mov     r14d, r8d
0x180024322  mov     rdi, rdx
0x180024325  mov     rbp, rcx
0x180024328  test    r8b, 2
0x18002432c  jz      short loc_180024379
0x18002432e  lea     rax, aMetrics; "metrics"
0x180024335  mov     byte ptr [rsi], 7
0x180024338  mov     [rdx], rax
0x18002433b  mov     rcx, rdi; this
0x18002433e  xor     edx, edx; bool
0x180024340  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180024345  mov     rax, [rdi+80h]
0x18002434c  cmp     rax, 19h
0x180024350  jnb     short loc_180024363
0x180024352  mov     dword ptr [rdi+rax*4+1Ch], 0
0x18002435a  inc     qword ptr [rdi+80h]
0x180024361  jmp     short loc_180024367
0x180024363  mov     byte ptr [rdi+18h], 1
0x180024367  mov     rcx, rdi; this
0x18002436a  mov     dword ptr [rbp+0B8h], 0
0x180024374  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x180024379  test    r14b, 1
0x18002437d  jz      short loc_1800243EA
0x18002437f  lea     rax, aTest; "test"
0x180024386  mov     byte ptr [rsi], 4
0x180024389  xor     edx, edx; bool
0x18002438b  mov     [rdi], rax
0x18002438e  mov     rcx, rdi; this
0x180024391  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180024396  mov     rax, [rdi+80h]
0x18002439d  cmp     rax, 19h
0x1800243a1  jnb     short loc_1800243B4
0x1800243a3  mov     dword ptr [rdi+rax*4+1Ch], 0
0x1800243ab  inc     qword ptr [rdi+80h]
0x1800243b2  jmp     short loc_1800243B8
0x1800243b4  mov     byte ptr [rdi+18h], 1
0x1800243b8  lea     rax, aTaskstatus; "taskStatus"
0x1800243bf  mov     byte ptr [rsi], 0Ah
0x1800243c2  mov     [rdi], rax
0x1800243c5  lea     rdx, [rbp+110h]
0x1800243cc  mov     eax, 10h
0x1800243d1  test    rbp, rbp
0x1800243d4  mov     rcx, rdi; this
0x1800243d7  cmovz   rdx, rax
0x1800243db  mov     edx, [rdx]; unsigned int
0x1800243dd  call    ?saveValue@output_archive@tson@@QEAAXK@Z; tson::output_archive::saveValue(ulong)
0x1800243e2  mov     rcx, rdi; this
0x1800243e5  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x1800243ea  add     rsp, 20h
0x1800243ee  pop     r14
0x1800243f0  pop     rdi
0x1800243f1  pop     rsi
0x1800243f2  pop     rbp
0x1800243f3  pop     rbx
0x1800243f4  retn
```
