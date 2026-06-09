# Ivy::Extras::CreateDataOverrideTransform(Ivy::ChartDataDimension,uint,double,Ivy::Extras::DataOverridePolicy,Ivy::Extras::DataOverrideRange const *,uint,Ivy::Extras::IChartDataTransform * &)

- ea: `0x180111a20`
- end: `0x180111b5c`
- name: `?CreateDataOverrideTransform@Extras@Ivy@@YAXW4ChartDataDimension@2@INW4DataOverridePolicy@12@PEBUDataOverrideRange@12@IAEAPEAUIChartDataTransform@12@@Z`
- size: `316`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, __int64, int, __int64 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x180015c38`
- `0x18007fe9c`
- `0x180094cac`
- `0x180111a20`
- `0x180111b5c`
- `0x180112904`
- `0x18016ba7c`
- `0x18016eaf0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180111a9b`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x180111a9b`

## string_xrefs

- `0x180111b45`: `CreateDataOverrideTransform() can only override numeric data.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Ivy::Extras::CreateDataOverrideTransform(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        __int64 a5,
        int a6,
        __int64 *a7)
{
  int v9; // r12d
  __int64 v10; // rbx
  int v11; // esi
  void *v12; // rax
  int v13; // r9d
  __int64 result; // rax
  __int64 v15; // rdi
  void (__fastcall ***v16)(_QWORD); // rcx

  try
  {
    v9 = a1;
    v10 = 0;
    *a7 = 0;
    if ( a4 == 2 )
    {
      if ( !a5 || (v11 = a6) == 0 )
      {
        sub_180015C38(508643403);
        sub_180112904();
      }
    }
    else
    {
      v11 = a6;
    }
    if ( (unsigned int)sub_180094CAC(a1) )
    {
      sub_180015C38(508643402);
      sub_18007FE9C(508643402, 0, "CreateDataOverrideTransform() can only override numeric data.");
    }
    v12 = malloc(0xB0u);
    if ( !v12 )
      Concurrency::cancel_current_task();
    result = sub_180111B5C((_DWORD)v12, v9, a2, v13, a4, a5, v11);
    v15 = result;
    if ( result )
    {
      v16 = (void (__fastcall ***)(_QWORD))(result + *(int *)(*(_QWORD *)(result + 8) + 4LL) + 8LL);
      (**v16)(v16);
      result = *(_QWORD *)(v15 + 8);
      v10 = v15 + *(int *)(result + 8) + 8LL;
    }
    *a7 = v10;
  }
  catch ( ... )
  {
    result = sub_180001030();
    if ( *(_QWORD *)(result + 80) && *(_DWORD *)(result + 88) <= 3u )
    {
      result = sub_180001030();
      if ( *(_QWORD *)(result + 80) )
        return (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64 *))(**(_QWORD **)(result + 80)
                                                                                       + 16LL))(
                 *(_QWORD *)(result + 80),
                 3,
                 1,
                 508643401,
                 &qword_1801AB2B8);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180111a20  mov     rax, rsp
0x180111a23  mov     [rax+8], rbx
0x180111a27  mov     [rax+10h], rsi
0x180111a2b  mov     [rax+18h], rdi
0x180111a2f  mov     [rax+20h], r12
0x180111a33  push    r13
0x180111a35  push    r14
0x180111a37  push    r15
0x180111a39  sub     rsp, 50h
0x180111a3d  movaps  xmmword ptr [rax-28h], xmm6
0x180111a41  mov     r15d, r9d
0x180111a44  movaps  xmm6, xmm2
0x180111a47  mov     r13d, edx
0x180111a4a  mov     r12d, ecx
0x180111a4d  xor     ebx, ebx
0x180111a4f  mov     r14, [rsp+68h+arg_30]
0x180111a57  mov     [r14], rbx
0x180111a5a  mov     rdi, [rsp+68h+arg_20]
0x180111a62  cmp     r9d, 2
0x180111a66  jnz     short loc_180111A82
0x180111a68  test    rdi, rdi
0x180111a6b  jz      loc_180111B2A
0x180111a71  mov     esi, [rsp+68h+arg_28]
0x180111a78  test    esi, esi
0x180111a7a  jz      loc_180111B2A
0x180111a80  jmp     short loc_180111A89
0x180111a82  mov     esi, [rsp+68h+arg_28]
0x180111a89  call    sub_180094CAC
0x180111a8e  test    eax, eax
0x180111a90  jnz     loc_180111B39
0x180111a96  mov     ecx, 0B0h; Size
0x180111a9b  call    cs:malloc
0x180111aa1  test    rax, rax
0x180111aa4  jz      loc_180111B55
0x180111aaa  mov     [rsp+68h+arg_30], rax
0x180111ab2  mov     [rsp+68h+var_38], esi
0x180111ab6  mov     [rsp+68h+var_40], rdi
0x180111abb  mov     [rsp+68h+var_48], r15d
0x180111ac0  movaps  xmm3, xmm6
0x180111ac3  mov     r8d, r13d
0x180111ac6  mov     edx, r12d
0x180111ac9  mov     rcx, rax
0x180111acc  call    sub_180111B5C
0x180111ad1  mov     rdi, rax
0x180111ad4  test    rax, rax
0x180111ad7  jz      short loc_180111B03
0x180111ad9  mov     rcx, [rax+8]
0x180111add  movsxd  rcx, dword ptr [rcx+4]
0x180111ae1  add     rcx, 8
0x180111ae5  add     rcx, rax
0x180111ae8  mov     rdx, [rcx]
0x180111aeb  mov     rax, [rdx]
0x180111aee  call    cs:__guard_dispatch_icall_fptr
0x180111af4  mov     rax, [rdi+8]
0x180111af8  movsxd  rbx, dword ptr [rax+8]
0x180111afc  add     rbx, 8
0x180111b00  add     rbx, rdi
0x180111b03  mov     [r14], rbx
0x180111b06  lea     r11, [rsp+68h+var_18]
0x180111b0b  mov     rbx, [r11+20h]
0x180111b0f  mov     rsi, [r11+28h]
0x180111b13  mov     rdi, [r11+30h]
0x180111b17  mov     r12, [r11+38h]
0x180111b1b  movaps  xmm6, [rsp+68h+var_28]
0x180111b20  mov     rsp, r11
0x180111b23  pop     r15
0x180111b25  pop     r14
0x180111b27  pop     r13
0x180111b29  retn
0x180111b2a  mov     ecx, 1E51484Bh
0x180111b2f  call    sub_180015C38
0x180111b34  call    sub_180112904
0x180111b39  mov     ebx, 1E51484Ah
0x180111b3e  mov     ecx, ebx
0x180111b40  call    sub_180015C38
0x180111b45  lea     r8, aCreatedataover_0; "CreateDataOverrideTransform() can only "...
0x180111b4c  xor     edx, edx
0x180111b4e  mov     ecx, ebx
0x180111b50  call    sub_18007FE9C
0x180111b55  call    ?cancel_current_task@Concurrency@@YAXXZ_1; Concurrency::cancel_current_task(void)
```
