# CGroupPolicyLog::DeleteRecord(CGroupPolicyRecord *,int)

- ea: `0x18002a4a4`
- end: `0x18002a575`
- name: `?DeleteRecord@CGroupPolicyLog@@QEAAJPEAVCGroupPolicyRecord@@H@Z`
- size: `209`
- prototype: `__int64 __fastcall(CGroupPolicyLog *__hidden this, struct CGroupPolicyRecord *, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18000a7c0`
- `0x18000aeb4`
- `0x18002a3d4`

## callees

- `0x18002a4a4`
- `0x18002c010`

## import_xrefs

- `USERENV!RsopResetPolicySettingStatus` at `0x18002a4dd`
- `USERENV!RsopResetPolicySettingStatus` at `0x18002a4dd`
- `OLEAUT32!__imp_VariantInit` at `0x18002a4c9`
- `OLEAUT32!__imp_VariantInit` at `0x18002a4c9`
- `OLEAUT32!__imp_VariantClear` at `0x18002a4ee`
- `OLEAUT32!__imp_VariantClear` at `0x18002a55d`
- `OLEAUT32!__imp_VariantClear` at `0x18002a4ee`
- `OLEAUT32!__imp_VariantClear` at `0x18002a55d`

## string_xrefs

- `0x18002a50a`: `__PATH`

## pseudocode

```c
__int64 __fastcall CGroupPolicyLog::DeleteRecord(CGroupPolicyLog *this, struct CGroupPolicyRecord *a2, int a3)
{
  HRESULT v6; // esi
  int v8; // ebx
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h]

  v10 = 0;
  VariantInit(&pvarg);
  if ( a3
    && (v6 = RsopResetPolicySettingStatus(0, *((IWbemServices **)this + 4), *((IWbemClassObject **)a2 + 1)), v6 < 0) )
  {
    VariantClear(&pvarg);
    return (unsigned int)v6;
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, const OLECHAR *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(**((_QWORD **)a2 + 1)
                                                                                                  + 32LL))(
           *((_QWORD *)a2 + 1),
           L"__PATH",
           0,
           &pvarg,
           0,
           0);
    if ( v8 >= 0 )
      v8 = (*(__int64 (__fastcall **)(_QWORD, LONGLONG, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 4) + 128LL))(
             *((_QWORD *)this + 4),
             pvarg.llVal,
             0,
             0,
             0);
    VariantClear(&pvarg);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x18002a4a4  mov     rax, rsp
0x18002a4a7  mov     [rax+8], rbx
0x18002a4ab  mov     [rax+10h], rsi
0x18002a4af  push    rdi
0x18002a4b0  sub     rsp, 60h
0x18002a4b4  mov     rdi, rcx
0x18002a4b7  mov     qword ptr [rax-10h], 0
0x18002a4bf  lea     rcx, [rax-28h]; pvarg
0x18002a4c3  mov     esi, r8d
0x18002a4c6  mov     rbx, rdx
0x18002a4c9  call    cs:__imp_VariantInit
0x18002a4cf  test    esi, esi
0x18002a4d1  jz      short loc_18002A4F8
0x18002a4d3  mov     r8, [rbx+8]; pSettingInstance
0x18002a4d7  xor     ecx, ecx; dwFlags
0x18002a4d9  mov     rdx, [rdi+20h]; pServices
0x18002a4dd  call    cs:__imp_RsopResetPolicySettingStatus
0x18002a4e3  mov     esi, eax
0x18002a4e5  test    eax, eax
0x18002a4e7  jns     short loc_18002A4F8
0x18002a4e9  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18002a4ee  call    cs:__imp_VariantClear
0x18002a4f4  mov     eax, esi
0x18002a4f6  jmp     short loc_18002A565
0x18002a4f8  mov     rcx, [rbx+8]
0x18002a4fc  lea     r9, [rsp+68h+pvarg]
0x18002a501  mov     [rsp+68h+var_40], 0
0x18002a50a  lea     rdx, psz; "__PATH"
0x18002a511  xor     r8d, r8d
0x18002a514  mov     [rsp+68h+var_48], 0
0x18002a51d  mov     rax, [rcx]
0x18002a520  mov     rax, [rax+20h]
0x18002a524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a529  mov     ebx, eax
0x18002a52b  test    eax, eax
0x18002a52d  js      short loc_18002A558
0x18002a52f  mov     rcx, [rdi+20h]
0x18002a533  xor     r9d, r9d
0x18002a536  mov     rdx, qword ptr [rsp+68h+pvarg+8]
0x18002a53b  xor     r8d, r8d
0x18002a53e  mov     [rsp+68h+var_48], 0
0x18002a547  mov     rax, [rcx]
0x18002a54a  mov     rax, [rax+80h]
0x18002a551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a556  mov     ebx, eax
0x18002a558  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18002a55d  call    cs:__imp_VariantClear
0x18002a563  mov     eax, ebx
0x18002a565  mov     rbx, [rsp+68h+arg_0]
0x18002a56a  mov     rsi, [rsp+68h+arg_8]
0x18002a56f  add     rsp, 60h
0x18002a573  pop     rdi
0x18002a574  retn
```
