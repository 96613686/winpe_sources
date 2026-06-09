# Windows::Json::to_setting_value(web::json::value const &)

- ea: `0x180052cb8`
- end: `0x180052e93`
- name: `?to_setting_value@Json@Windows@@YA?AV?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBVvalue@json@web@@@Z`
- size: `475`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180040a9c`

## callees

- `0x180009380`
- `0x180033b00`
- `0x1800345b0`
- `0x180052cb8`
- `0x180058abc`
- `0x18005c5e0`

## string_xrefs

- `0x180052e70`: `Invalid json number type`

## pseudocode

```c
__int64 __fastcall Windows::Json::to_setting_value(__int64 a1, __int64 **a2)
{
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rax
  bool v10; // cl
  bool v11; // zf
  __int64 *v12; // rcx
  __int64 (__fastcall *v13)(__int64 *); // rax
  __int64 v14; // rax
  int v15; // ecx
  __int64 v16; // rax
  int v17; // edx
  __int64 v18; // rax
  double v19; // xmm0_8
  unsigned __int64 v20; // rcx
  double v21; // rax
  __int64 v22; // rax
  __int128 v23; // xmm0
  __m128i v24; // xmm1
  __m128i si128; // xmm0
  __int128 pExceptionObject; // [rsp+28h] [rbp-30h] BYREF
  __m128i v28; // [rsp+38h] [rbp-20h]

  v4 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 88))(*a2);
  v5 = **a2;
  if ( v4 == 2 )
  {
    v6 = (*(__int64 (**)(void))(v5 + 176))();
    std::wstring::wstring(a1, v6);
    *(_BYTE *)(a1 + 32) = 2;
    return a1;
  }
  v7 = (*(__int64 (**)(void))(v5 + 88))();
  v8 = **a2;
  if ( v7 )
  {
    v11 = (*(unsigned int (**)(void))(v8 + 88))() == 1;
    v22 = **a2;
    if ( !v11 )
    {
      (*(void (__fastcall **)(__int64 *, __int128 *))(v22 + 80))(*a2, &pExceptionObject);
      v23 = pExceptionObject;
      LOWORD(pExceptionObject) = 0;
      v24 = v28;
      *(_OWORD *)a1 = v23;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      *(__m128i *)(a1 + 16) = v24;
      *(_BYTE *)(a1 + 32) = 2;
      v28 = si128;
      std::wstring::~wstring(&pExceptionObject);
      return a1;
    }
    v15 = (*(unsigned __int8 (**)(void))(v22 + 136))() != 0;
    goto LABEL_11;
  }
  v9 = (*(__int64 (**)(void))(v8 + 112))();
  v10 = *(_DWORD *)(v9 + 8) < 2u && *(_QWORD *)v9 <= 0xFFFFFFFF;
  v11 = !v10;
  v12 = *a2;
  v13 = *(__int64 (__fastcall **)(__int64 *))(**a2 + 112);
  if ( !v11 )
  {
    v14 = v13(v12);
    if ( *(_DWORD *)(v14 + 8) == 2 )
      v15 = (int)*(double *)v14;
    else
      v15 = *(_DWORD *)v14;
LABEL_11:
    *(_DWORD *)a1 = v15;
    *(_BYTE *)(a1 + 32) = 0;
    return a1;
  }
  v16 = v13(v12);
  v17 = *(_DWORD *)(v16 + 8);
  if ( v17 )
  {
    if ( v17 == 1 )
      goto LABEL_16;
LABEL_27:
    std::runtime_error::runtime_error((std::runtime_error *)&pExceptionObject, "Invalid json number type");
    throw (std::runtime_error *)&pExceptionObject;
  }
  if ( *(__int64 *)v16 < 0 )
    goto LABEL_27;
LABEL_16:
  v18 = (*(__int64 (__fastcall **)(__int64 *))(**a2 + 112))(*a2);
  if ( *(_DWORD *)(v18 + 8) == 2 )
  {
    v19 = *(double *)v18;
    v20 = 0;
    if ( *(double *)v18 >= 9.223372036854776e18 )
    {
      v19 = v19 - 9.223372036854776e18;
      if ( v19 < 9.223372036854776e18 )
        v20 = 0x8000000000000000uLL;
    }
    *(_QWORD *)&v21 = v20 + (unsigned int)(int)v19;
  }
  else
  {
    v21 = *(double *)v18;
  }
  *(double *)a1 = v21;
  *(_BYTE *)(a1 + 32) = 1;
  return a1;
}

```

## disassembly

```asm
0x180052cb8  mov     [rsp+arg_0], rbx
0x180052cbd  mov     [rsp+arg_8], rsi
0x180052cc2  push    rdi
0x180052cc3  sub     rsp, 50h
0x180052cc7  mov     rbx, rcx
0x180052cca  mov     rdi, rdx
0x180052ccd  mov     rcx, [rdx]
0x180052cd0  xor     esi, esi
0x180052cd2  mov     rax, [rcx]
0x180052cd5  mov     rax, [rax+58h]
0x180052cd9  call    _guard_dispatch_icall
0x180052cde  mov     rcx, [rdi]
0x180052ce1  mov     rdx, [rcx]
0x180052ce4  cmp     eax, 2
0x180052ce7  jnz     short loc_180052D09
0x180052ce9  mov     rax, [rdx+0B0h]
0x180052cf0  call    _guard_dispatch_icall
0x180052cf5  mov     rdx, rax
0x180052cf8  mov     rcx, rbx
0x180052cfb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180052d00  mov     byte ptr [rbx+20h], 2
0x180052d04  jmp     loc_180052E5D
0x180052d09  mov     rax, [rdx+58h]
0x180052d0d  call    _guard_dispatch_icall
0x180052d12  mov     rcx, [rdi]
0x180052d15  mov     rdx, [rcx]
0x180052d18  test    eax, eax
0x180052d1a  jnz     loc_180052DF1
0x180052d20  mov     rax, [rdx+70h]
0x180052d24  call    _guard_dispatch_icall
0x180052d29  mov     edx, [rax+8]
0x180052d2c  test    edx, edx
0x180052d2e  jz      short loc_180052D3A
0x180052d30  cmp     edx, 1
0x180052d33  jz      short loc_180052D3A
0x180052d35  mov     cl, sil
0x180052d38  jmp     short loc_180052D45
0x180052d3a  mov     ecx, 0FFFFFFFFh
0x180052d3f  cmp     [rax], rcx
0x180052d42  setbe   cl
0x180052d45  mov     rdx, [rdi]
0x180052d48  test    cl, cl
0x180052d4a  mov     rcx, rdx
0x180052d4d  mov     rax, [rdx]
0x180052d50  mov     rax, [rax+70h]
0x180052d54  jz      short loc_180052D75
0x180052d56  call    _guard_dispatch_icall
0x180052d5b  cmp     dword ptr [rax+8], 2
0x180052d5f  jnz     short loc_180052D68
0x180052d61  cvttsd2si rcx, qword ptr [rax]
0x180052d66  jmp     short loc_180052D6A
0x180052d68  mov     ecx, [rax]
0x180052d6a  mov     [rbx], ecx
0x180052d6c  mov     [rbx+20h], sil
0x180052d70  jmp     loc_180052E5D
0x180052d75  call    _guard_dispatch_icall
0x180052d7a  mov     edx, [rax+8]
0x180052d7d  test    edx, edx
0x180052d7f  jz      short loc_180052D8C
0x180052d81  cmp     edx, 1
0x180052d84  jnz     loc_180052E70
0x180052d8a  jmp     short loc_180052D9B
0x180052d8c  mov     rax, [rax]
0x180052d8f  shr     rax, 3Fh
0x180052d93  test    al, al
0x180052d95  jnz     loc_180052E70
0x180052d9b  mov     rcx, [rdi]
0x180052d9e  mov     rax, [rcx]
0x180052da1  mov     rax, [rax+70h]
0x180052da5  call    _guard_dispatch_icall
0x180052daa  cmp     dword ptr [rax+8], 2
0x180052dae  jnz     short loc_180052DE5
0x180052db0  movsd   xmm0, qword ptr [rax]
0x180052db4  xor     ecx, ecx
0x180052db6  movsd   xmm1, cs:__real@43e0000000000000
0x180052dbe  comisd  xmm0, xmm1
0x180052dc2  jb      short loc_180052DDB
0x180052dc4  subsd   xmm0, xmm1
0x180052dc8  comisd  xmm0, xmm1
0x180052dcc  jnb     short loc_180052DDB
0x180052dce  mov     rax, 8000000000000000h
0x180052dd8  mov     rcx, rax
0x180052ddb  cvttsd2si rax, xmm0
0x180052de0  add     rax, rcx
0x180052de3  jmp     short loc_180052DE8
0x180052de5  mov     rax, [rax]
0x180052de8  mov     [rbx], rax
0x180052deb  mov     byte ptr [rbx+20h], 1
0x180052def  jmp     short loc_180052E5D
0x180052df1  mov     rax, [rdx+58h]
0x180052df5  call    _guard_dispatch_icall
0x180052dfa  mov     rcx, [rdi]
0x180052dfd  cmp     eax, 1
0x180052e00  mov     rax, [rcx]
0x180052e03  jnz     short loc_180052E1D
0x180052e05  mov     rax, [rax+88h]
0x180052e0c  call    _guard_dispatch_icall
0x180052e11  test    al, al
0x180052e13  mov     ecx, esi
0x180052e15  setnz   cl
0x180052e18  jmp     loc_180052D6A
0x180052e1d  mov     rax, [rax+50h]
0x180052e21  lea     rdx, [rsp+58h+pExceptionObject]
0x180052e26  call    _guard_dispatch_icall
0x180052e2b  movups  xmm0, [rsp+58h+pExceptionObject]
0x180052e30  lea     rcx, [rsp+58h+pExceptionObject]; void *
0x180052e35  mov     word ptr [rsp+58h+pExceptionObject], si
0x180052e3a  movups  xmm1, [rsp+58h+var_20]
0x180052e3f  movups  xmmword ptr [rbx], xmm0
0x180052e42  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180052e4a  movups  xmmword ptr [rbx+10h], xmm1
0x180052e4e  mov     byte ptr [rbx+20h], 2
0x180052e52  movdqu  [rsp+58h+var_20], xmm0
0x180052e58  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052e5d  mov     rsi, [rsp+58h+arg_8]
0x180052e62  mov     rax, rbx
0x180052e65  mov     rbx, [rsp+58h+arg_0]
0x180052e6a  add     rsp, 50h
0x180052e6e  pop     rdi
0x180052e6f  retn
0x180052e70  lea     rdx, aInvalidJsonNum; "Invalid json number type"
0x180052e77  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180052e7c  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x180052e81  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x180052e88  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180052e8d  call    _CxxThrowException
```
