# tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::serialize(tson::output_archive &,tip2::details::serialize_options)

- ea: `0x180009810`
- end: `0x18000993f`
- name: `?serialize@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@EEAAXAEAVoutput_archive@tson@@W4serialize_options@23@@Z`
- size: `303`
- prototype: `void __fastcall(__int64, __int64, char)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180009810`
- `0x18000d3b0`
- `0x18000d8d0`
- `0x18000dac0`
- `0x18000de10`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::serialize(
        __int64 a1,
        __int64 a2,
        char a3)
{
  void *v3; // rdi
  unsigned __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // rbx

  v3 = 0;
  if ( (a3 & 2) != 0 )
  {
    *(_BYTE *)(a2 + 8) = 7;
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
    *(_BYTE *)(a2 + 8) = 4;
    *(_QWORD *)a2 = "test";
    tson::output_archive::write_name((tson::output_archive *)a2, 0);
    v10 = *(_QWORD *)(a2 + 128);
    if ( v10 >= 0x19 )
    {
      *(_BYTE *)(a2 + 24) = 1;
    }
    else
    {
      *(_DWORD *)(a2 + 4 * v10 + 28) = 0;
      ++*(_QWORD *)(a2 + 128);
    }
    *(_BYTE *)(a2 + 8) = 11;
    v11 = a1 + 264;
    if ( !a1 )
      v11 = 16;
    *(_QWORD *)a2 = "packageName";
    v12 = *(_QWORD *)(v11 + 16);
    if ( v12 )
    {
      v3 = (void *)v11;
      if ( *(_QWORD *)(v11 + 24) > 7u )
        v3 = *(void **)v11;
    }
    LOBYTE(v9) = 24;
    LOBYTE(v8) = v3 == 0;
    if ( (unsigned __int8)tson::output_archive::write_type(a2, v8, v9) )
      tson::output_archive::write_string_bytes((tson::output_archive *)a2, v12, v3, 2 * v12);
    tson::output_archive::finishNode((tson::output_archive *)a2);
  }
}

```

## disassembly

```asm
0x180009810  mov     [rsp+arg_0], rbx
0x180009815  mov     [rsp+arg_10], rbp
0x18000981a  mov     [rsp+arg_18], rsi
0x18000981f  push    rdi
0x180009820  push    r14
0x180009822  push    r15
0x180009824  sub     rsp, 20h
0x180009828  xor     edi, edi
0x18000982a  mov     r15d, r8d
0x18000982d  mov     rsi, rdx
0x180009830  mov     rbp, rcx
0x180009833  test    r8b, 2
0x180009837  jz      short loc_18000987D
0x180009839  lea     rax, aMetrics; "metrics"
0x180009840  mov     byte ptr [rdx+8], 7
0x180009844  mov     [rdx], rax
0x180009847  mov     rcx, rsi; this
0x18000984a  xor     edx, edx; bool
0x18000984c  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x180009851  mov     rax, [rsi+80h]
0x180009858  cmp     rax, 19h
0x18000985c  jnb     short loc_18000986B
0x18000985e  mov     [rsi+rax*4+1Ch], edi
0x180009862  inc     qword ptr [rsi+80h]
0x180009869  jmp     short loc_18000986F
0x18000986b  mov     byte ptr [rsi+18h], 1
0x18000986f  mov     rcx, rsi; this
0x180009872  mov     [rbp+0B8h], edi
0x180009878  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x18000987d  test    r15b, 1
0x180009881  jz      loc_180009926
0x180009887  lea     rax, aTest; "test"
0x18000988e  mov     byte ptr [rsi+8], 4
0x180009892  xor     edx, edx; bool
0x180009894  mov     [rsi], rax
0x180009897  mov     rcx, rsi; this
0x18000989a  call    ?write_name@output_archive@tson@@AEAA_N_N@Z; tson::output_archive::write_name(bool)
0x18000989f  mov     rax, [rsi+80h]
0x1800098a6  cmp     rax, 19h
0x1800098aa  jnb     short loc_1800098B9
0x1800098ac  mov     [rsi+rax*4+1Ch], edi
0x1800098b0  inc     qword ptr [rsi+80h]
0x1800098b7  jmp     short loc_1800098BD
0x1800098b9  mov     byte ptr [rsi+18h], 1
0x1800098bd  test    rbp, rbp
0x1800098c0  mov     byte ptr [rsi+8], 0Bh
0x1800098c4  mov     ecx, 10h
0x1800098c9  lea     rax, [rbp+108h]
0x1800098d0  cmovz   rax, rcx
0x1800098d4  lea     rcx, aPackagename; "packageName"
0x1800098db  mov     [rsi], rcx
0x1800098de  mov     rbx, [rax+10h]
0x1800098e2  test    rbx, rbx
0x1800098e5  jz      short loc_1800098F4
0x1800098e7  cmp     qword ptr [rax+18h], 7
0x1800098ec  mov     rdi, rax
0x1800098ef  jbe     short loc_1800098F4
0x1800098f1  mov     rdi, [rax]
0x1800098f4  mov     rax, rdi
0x1800098f7  mov     r8b, 18h
0x1800098fa  test    rax, rax
0x1800098fd  mov     rcx, rsi
0x180009900  setz    dl
0x180009903  call    ?write_type@output_archive@tson@@AEAA_N_NW4archive_marker@details@2@@Z; tson::output_archive::write_type(bool,tson::details::archive_marker)
0x180009908  test    al, al
0x18000990a  jz      short loc_18000991E
0x18000990c  lea     r9, [rbx+rbx]; unsigned __int64
0x180009910  mov     r8, rdi; void *
0x180009913  mov     rdx, rbx; unsigned __int64
0x180009916  mov     rcx, rsi; this
0x180009919  call    ?write_string_bytes@output_archive@tson@@AEAAX_KPEAX0@Z; tson::output_archive::write_string_bytes(unsigned __int64,void *,unsigned __int64)
0x18000991e  mov     rcx, rsi; this
0x180009921  call    ?finishNode@output_archive@tson@@QEAAXXZ; tson::output_archive::finishNode(void)
0x180009926  mov     rbx, [rsp+38h+arg_0]
0x18000992b  mov     rbp, [rsp+38h+arg_10]
0x180009930  mov     rsi, [rsp+38h+arg_18]
0x180009935  add     rsp, 20h
0x180009939  pop     r15
0x18000993b  pop     r14
0x18000993d  pop     rdi
0x18000993e  retn
```
