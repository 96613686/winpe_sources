# SrpInvokePlugins

- ea: `0x1400237dc`
- end: `0x14002392c`
- name: `SrpInvokePlugins`
- size: `336`
- prototype: `__int64 __fastcall(__int64, int, __int128 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140030ff0`
- `0x140034550`

## callees

- `0x140001d30`
- `0x1400237dc`
- `0x1400328b0`
- `0x140036e80`

## pseudocode

```c
__int64 __fastcall SrpInvokePlugins(__int64 a1, int a2, __int128 *a3)
{
  __int64 v4; // r13
  __int64 v6; // rax
  __int64 v7; // rdi
  unsigned int i; // r14d
  __int64 result; // rax
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  void *v13; // rbx
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  int v16; // r15d
  void *v17; // [rsp+30h] [rbp-39h] BYREF
  __int128 v18; // [rsp+40h] [rbp-29h] BYREF
  __int128 v19; // [rsp+50h] [rbp-19h]
  __int128 v20; // [rsp+60h] [rbp-9h]
  __int128 v21; // [rsp+70h] [rbp+7h]
  __int64 v22; // [rsp+80h] [rbp+17h]
  __int64 *v23; // [rsp+88h] [rbp+1Fh]
  int v24; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = a2;
  if ( *(int *)(a1 + 208) >= 0 )
  {
    v6 = *(_QWORD *)(a1 + 216);
    if ( v6 )
    {
      v7 = v6 + *(unsigned int *)(v6 + 8);
      for ( i = 0; i < *(_DWORD *)(*(_QWORD *)(a1 + 216) + 12LL); ++i )
      {
        v17 = 0;
        v24 = 0;
        result = SrppGetPluginPolicy(a1, (int)a1 + 24 * ((int)v4 + 10), v7, (unsigned int)&v17, (__int64)&v24);
        if ( (int)result >= 0 )
        {
          v10 = *a3;
          v11 = a3[1];
          v25 = 0;
          v18 = v10;
          v12 = a3[2];
          *((_QWORD *)&v18 + 1) = a1 + 24 * (v4 + 10);
          v13 = v17;
          v19 = v11;
          v14 = a3[3];
          LODWORD(v19) = v24;
          v20 = v12;
          v15 = a3[4];
          *(_QWORD *)&v18 = v7;
          v21 = v14;
          v22 = v15;
          v23 = &v25;
          *((_QWORD *)&v19 + 1) = v17;
          v16 = AipForEachPlugin(
                  (__int64 (__fastcall *)(__int64 *, __int64 *, __int64))PluginInvokeCallback,
                  (__int64)&v18);
          AiFree(v13);
          if ( v16 < 0 )
            return (unsigned int)v16;
          result = (unsigned int)v25;
          if ( (int)v25 < 0 )
            return result;
        }
        else if ( (_DWORD)result != -1073741275 )
        {
          return result;
        }
        v7 += 36;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1400237dc  mov     [rsp-8+arg_8], rbx
0x1400237e1  push    rbp
0x1400237e2  push    rsi
0x1400237e3  push    rdi
0x1400237e4  push    r12
0x1400237e6  push    r13
0x1400237e8  push    r14
0x1400237ea  push    r15
0x1400237ec  lea     rbp, [rsp-27h]
0x1400237f1  sub     rsp, 90h
0x1400237f8  cmp     dword ptr [rcx+0D0h], 0
0x1400237ff  mov     r12, r8
0x140023802  movsxd  r13, edx
0x140023805  mov     rsi, rcx
0x140023808  jl      loc_14002390E
0x14002380e  mov     rax, [rcx+0D8h]
0x140023815  test    rax, rax
0x140023818  jz      loc_14002390E
0x14002381e  mov     edi, [rax+8]
0x140023821  add     rdi, rax
0x140023824  xor     r14d, r14d
0x140023827  mov     rax, [rsi+0D8h]
0x14002382e  cmp     r14d, [rax+0Ch]
0x140023832  jnb     loc_14002390E
0x140023838  lea     rax, [r13+0Ah]
0x14002383c  mov     [rbp+57h+var_90], 0
0x140023844  lea     rax, [rax+rax*2]
0x140023848  mov     [rbp+57h+arg_0], 0
0x14002384f  lea     rbx, [rsi+rax*8]
0x140023853  mov     r8, rdi
0x140023856  lea     rax, [rbp+57h+arg_0]
0x14002385a  mov     rdx, rbx
0x14002385d  lea     r9, [rbp+57h+var_90]
0x140023861  mov     [rsp+0C0h+var_A0], rax
0x140023866  mov     rcx, rsi
0x140023869  call    SrppGetPluginPolicy
0x14002386e  test    eax, eax
0x140023870  jns     short loc_14002387F
0x140023872  cmp     eax, 0C0000225h
0x140023877  jnz     loc_140023910
0x14002387d  jmp     short loc_1400238FD
0x14002387f  movups  xmm0, xmmword ptr [r12]
0x140023884  mov     eax, [rbp+57h+arg_0]
0x140023887  lea     rdx, [rbp+57h+var_80]
0x14002388b  movups  xmm1, xmmword ptr [r12+10h]
0x140023891  lea     rcx, PluginInvokeCallback
0x140023898  mov     [rbp+57h+arg_18], 0
0x1400238a0  movaps  [rbp+57h+var_80], xmm0
0x1400238a4  movups  xmm0, xmmword ptr [r12+20h]
0x1400238aa  mov     qword ptr [rbp+57h+var_80+8], rbx
0x1400238ae  mov     rbx, [rbp+57h+var_90]
0x1400238b2  movaps  [rbp+57h+var_70], xmm1
0x1400238b6  movups  xmm1, xmmword ptr [r12+30h]
0x1400238bc  mov     dword ptr [rbp+57h+var_70], eax
0x1400238bf  lea     rax, [rbp+57h+arg_18]
0x1400238c3  movaps  [rbp+57h+var_60], xmm0
0x1400238c7  movups  xmm0, xmmword ptr [r12+40h]
0x1400238cd  mov     qword ptr [rbp+57h+var_80], rdi
0x1400238d1  movaps  [rbp+57h+var_50], xmm1
0x1400238d5  movaps  [rbp+57h+var_40], xmm0
0x1400238d9  mov     qword ptr [rbp+57h+var_40+8], rax
0x1400238dd  mov     qword ptr [rbp+57h+var_70+8], rbx
0x1400238e1  call    AipForEachPlugin
0x1400238e6  mov     rcx, rbx
0x1400238e9  mov     r15d, eax
0x1400238ec  call    AiFree
0x1400238f1  test    r15d, r15d
0x1400238f4  js      short loc_140023909
0x1400238f6  mov     eax, dword ptr [rbp+57h+arg_18]
0x1400238f9  test    eax, eax
0x1400238fb  js      short loc_140023910
0x1400238fd  inc     r14d
0x140023900  add     rdi, 24h ; '$'
0x140023904  jmp     loc_140023827
0x140023909  mov     eax, r15d
0x14002390c  jmp     short loc_140023910
0x14002390e  xor     eax, eax
0x140023910  mov     rbx, [rsp+0C0h+arg_8]
0x140023918  add     rsp, 90h
0x14002391f  pop     r15
0x140023921  pop     r14
0x140023923  pop     r13
0x140023925  pop     r12
0x140023927  pop     rdi
0x140023928  pop     rsi
0x140023929  pop     rbp
0x14002392a  retn
```
