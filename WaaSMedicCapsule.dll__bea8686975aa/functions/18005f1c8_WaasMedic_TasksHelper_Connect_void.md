# WaasMedic::TasksHelper::Connect(void)

- ea: `0x18005f1c8`
- end: `0x18005f375`
- name: `?Connect@TasksHelper@WaasMedic@@AEAAJXZ`
- size: `429`
- prototype: `__int64 __fastcall(LPVOID *ppv)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18005f9bc`

## callees

- `0x18002543c`
- `0x18005f1c8`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f222`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005f222`
- `OLEAUT32!__imp_VariantInit` at `0x18005f256`
- `OLEAUT32!__imp_VariantInit` at `0x18005f26e`
- `OLEAUT32!__imp_VariantInit` at `0x18005f287`
- `OLEAUT32!__imp_VariantInit` at `0x18005f29e`
- `OLEAUT32!__imp_VariantInit` at `0x18005f256`
- `OLEAUT32!__imp_VariantInit` at `0x18005f26e`
- `OLEAUT32!__imp_VariantInit` at `0x18005f287`
- `OLEAUT32!__imp_VariantInit` at `0x18005f29e`
- `OLEAUT32!__imp_VariantClear` at `0x18005f304`
- `OLEAUT32!__imp_VariantClear` at `0x18005f310`
- `OLEAUT32!__imp_VariantClear` at `0x18005f31c`
- `OLEAUT32!__imp_VariantClear` at `0x18005f328`
- `OLEAUT32!__imp_VariantClear` at `0x18005f304`
- `OLEAUT32!__imp_VariantClear` at `0x18005f310`
- `OLEAUT32!__imp_VariantClear` at `0x18005f31c`
- `OLEAUT32!__imp_VariantClear` at `0x18005f328`

## string_xrefs

- `0x18005f231`: `Unable to CoCreateInstance for Task Scheduler. hr=0x%08x`
- `0x18005f335`: `Error when connecting to Task Scheduler. hr=0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WaasMedic::TasksHelper::Connect(LPVOID *ppv)
{
  int v2; // edi
  HRESULT Instance; // eax
  LPVOID v4; // rdi
  __int64 (__fastcall *v5)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *); // rbx
  __int128 v6; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v8; // xmm8
  IRecordInfo *v9; // xmm9_8
  __int128 v10; // xmm6
  IRecordInfo *v11; // xmm7_8
  VARIANTARG v13; // [rsp+30h] [rbp-D0h] BYREF
  VARIANTARG v14; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG v15; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-88h] BYREF
  __int128 v17; // [rsp+90h] [rbp-70h] BYREF
  IRecordInfo *v18; // [rsp+A0h] [rbp-60h]
  __int128 v19; // [rsp+B0h] [rbp-50h] BYREF
  IRecordInfo *v20; // [rsp+C0h] [rbp-40h]
  __int128 v21; // [rsp+D0h] [rbp-30h] BYREF
  IRecordInfo *v22; // [rsp+E0h] [rbp-20h]
  VARIANTARG v23; // [rsp+F0h] [rbp-10h] BYREF

  v2 = 0;
  if ( !*((_BYTE *)ppv + 16) )
  {
    Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, ppv);
    v2 = Instance;
    if ( Instance >= 0 )
    {
      v4 = *ppv;
      v5 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *, __int128 *))(*(_QWORD *)*ppv + 80LL);
      VariantInit(&pvarg);
      v6 = *(_OWORD *)&pvarg.vt;
      pRecInfo = pvarg.pRecInfo;
      VariantInit(&v15);
      v8 = *(_OWORD *)&v15.vt;
      v9 = v15.pRecInfo;
      VariantInit(&v14);
      v10 = *(_OWORD *)&v14.vt;
      v11 = v14.pRecInfo;
      VariantInit(&v13);
      v17 = v6;
      v18 = pRecInfo;
      v19 = v8;
      v20 = v9;
      v21 = v10;
      v22 = v11;
      v23 = v13;
      v2 = v5(v4, &v23, &v21, &v19, &v17);
      VariantClear(&v13);
      VariantClear(&v14);
      VariantClear(&v15);
      VariantClear(&pvarg);
      if ( v2 >= 0 )
        *((_BYTE *)ppv + 16) = 1;
      else
        LogLevelW(2u, L"Error when connecting to Task Scheduler. hr=0x%08x", (unsigned int)v2);
    }
    else
    {
      LogLevelW(2u, L"Unable to CoCreateInstance for Task Scheduler. hr=0x%08x", (unsigned int)Instance);
    }
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18005f1c8  mov     rax, rsp
0x18005f1cb  push    rbp
0x18005f1cc  push    rbx
0x18005f1cd  push    rsi
0x18005f1ce  push    rdi
0x18005f1cf  lea     rbp, [rsp-78h]
0x18005f1d4  sub     rsp, 178h
0x18005f1db  movaps  xmmword ptr [rax-38h], xmm6
0x18005f1df  movaps  xmmword ptr [rax-48h], xmm7
0x18005f1e3  movaps  xmmword ptr [rax-58h], xmm8
0x18005f1e8  movaps  xmmword ptr [rax-68h], xmm9
0x18005f1ed  movaps  xmmword ptr [rax-78h], xmm10
0x18005f1f2  movaps  xmmword ptr [rax-88h], xmm11
0x18005f1fa  mov     rsi, rcx
0x18005f1fd  xor     edi, edi
0x18005f1ff  cmp     [rcx+10h], dil
0x18005f203  jnz     loc_18005F345
0x18005f209  mov     [rsp+190h+ppv], rcx; ppv
0x18005f20e  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x18005f215  xor     edx, edx; pUnkOuter
0x18005f217  lea     r8d, [rdi+1]; dwClsContext
0x18005f21b  lea     rcx, CLSID_TaskScheduler; rclsid
0x18005f222  call    cs:__imp_CoCreateInstance
0x18005f228  mov     edi, eax
0x18005f22a  test    eax, eax
0x18005f22c  jns     short loc_18005F247
0x18005f22e  mov     r8d, eax
0x18005f231  lea     rdx, aUnableToCocrea; "Unable to CoCreateInstance for Task Sch"...
0x18005f238  mov     ecx, 2; unsigned __int8
0x18005f23d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f242  jmp     loc_18005F345
0x18005f247  mov     rdi, [rsi]
0x18005f24a  mov     rax, [rdi]
0x18005f24d  mov     rbx, [rax+50h]
0x18005f251  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18005f256  call    cs:__imp_VariantInit
0x18005f25c  nop
0x18005f25d  movups  xmm10, xmmword ptr [rsp+190h+pvarg]
0x18005f263  movsd   xmm11, qword ptr [rbp+90h+pvarg+10h]
0x18005f269  lea     rcx, [rsp+190h+var_130]; pvarg
0x18005f26e  call    cs:__imp_VariantInit
0x18005f274  nop
0x18005f275  movups  xmm8, xmmword ptr [rsp+190h+var_130]
0x18005f27b  movsd   xmm9, qword ptr [rsp+190h+var_130+10h]
0x18005f282  lea     rcx, [rsp+190h+var_148]; pvarg
0x18005f287  call    cs:__imp_VariantInit
0x18005f28d  nop
0x18005f28e  movups  xmm6, xmmword ptr [rsp+190h+var_148]
0x18005f293  movsd   xmm7, qword ptr [rsp+190h+var_148+10h]
0x18005f299  lea     rcx, [rsp+190h+var_160]; pvarg
0x18005f29e  call    cs:__imp_VariantInit
0x18005f2a4  nop
0x18005f2a5  movups  xmm0, xmmword ptr [rsp+190h+var_160]
0x18005f2aa  movsd   xmm1, qword ptr [rsp+190h+var_160+10h]
0x18005f2b0  movaps  [rbp+90h+var_100], xmm10
0x18005f2b5  movsd   [rbp+90h+var_F0], xmm11
0x18005f2bb  movaps  [rbp+90h+var_E0], xmm8
0x18005f2c0  movsd   [rbp+90h+var_D0], xmm9
0x18005f2c6  movaps  [rbp+90h+var_C0], xmm6
0x18005f2ca  movsd   [rbp+90h+var_B0], xmm7
0x18005f2cf  movaps  [rbp+90h+var_A0], xmm0
0x18005f2d3  movsd   [rbp+90h+var_90], xmm1
0x18005f2d8  lea     rax, [rbp+90h+var_100]
0x18005f2dc  mov     [rsp+190h+ppv], rax
0x18005f2e1  lea     r9, [rbp+90h+var_E0]
0x18005f2e5  lea     r8, [rbp+90h+var_C0]
0x18005f2e9  lea     rdx, [rbp+90h+var_A0]
0x18005f2ed  mov     rcx, rdi
0x18005f2f0  mov     rax, rbx
0x18005f2f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2f8  mov     edi, eax
0x18005f2fa  mov     ebx, eax
0x18005f2fc  shr     ebx, 1Fh
0x18005f2ff  lea     rcx, [rsp+190h+var_160]; pvarg
0x18005f304  call    cs:__imp_VariantClear
0x18005f30a  nop
0x18005f30b  lea     rcx, [rsp+190h+var_148]; pvarg
0x18005f310  call    cs:__imp_VariantClear
0x18005f316  nop
0x18005f317  lea     rcx, [rsp+190h+var_130]; pvarg
0x18005f31c  call    cs:__imp_VariantClear
0x18005f322  nop
0x18005f323  lea     rcx, [rsp+190h+pvarg]; pvarg
0x18005f328  call    cs:__imp_VariantClear
0x18005f32e  test    bl, bl
0x18005f330  jz      short loc_18005F341
0x18005f332  mov     r8d, edi
0x18005f335  lea     rdx, aErrorWhenConne; "Error when connecting to Task Scheduler"...
0x18005f33c  jmp     loc_18005F238
0x18005f341  mov     byte ptr [rsi+10h], 1
0x18005f345  mov     eax, edi
0x18005f347  lea     r11, [rsp+190h+var_18]
0x18005f34f  movaps  xmm6, xmmword ptr [r11-18h]
0x18005f354  movaps  xmm7, xmmword ptr [r11-28h]
0x18005f359  movaps  xmm8, xmmword ptr [r11-38h]
0x18005f35e  movaps  xmm9, xmmword ptr [r11-48h]
0x18005f363  movaps  xmm10, xmmword ptr [r11-58h]
0x18005f368  movaps  xmm11, xmmword ptr [r11-68h]
0x18005f36d  mov     rsp, r11
0x18005f370  pop     rdi
0x18005f371  pop     rsi
0x18005f372  pop     rbx
0x18005f373  pop     rbp
0x18005f374  retn
```
