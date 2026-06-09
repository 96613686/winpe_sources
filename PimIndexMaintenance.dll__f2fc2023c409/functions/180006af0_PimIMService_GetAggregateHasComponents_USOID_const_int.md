# PimIMService::GetAggregateHasComponents(USOID const &,int *)

- ea: `0x180006af0`
- end: `0x180006ba5`
- name: `?GetAggregateHasComponents@PimIMService@@UEAAJAEBUUSOID@@PEAH@Z`
- size: `181`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, const struct USOID *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180002da8`
- `0x18000428c`
- `0x180006af0`
- `0x180021240`
- `0x180022010`

## string_xrefs

- `0x180006b63`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::GetAggregateHasComponents(PimIMService *this, const struct USOID *a2, int *a3)
{
  __int64 v3; // xmm0_8
  __int64 v5; // rcx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v10; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h] BYREF
  int v12; // [rsp+40h] [rbp-18h]

  v3 = *(_QWORD *)a2;
  v5 = *((_QWORD *)this + 27);
  v12 = *((_DWORD *)a2 + 2);
  v11 = v3;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, GUID *, __int64 *))(*(_QWORD *)v5 + 200LL))(
         v5,
         &v11,
         &IID_IAggregate,
         &v10);
  v7 = v6;
  if ( v6 == -2147023728 )
  {
    v8 = 0;
LABEL_6:
    *a3 = v8;
    v7 = 0;
    goto LABEL_7;
  }
  if ( v6 >= 0 )
  {
    v8 = 1;
    goto LABEL_6;
  }
  Log_HREvent(
    (unsigned int)v6,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
    2356);
LABEL_7:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v10);
  return v7;
}

```

## disassembly

```asm
0x180006af0  mov     r11, rsp
0x180006af3  mov     [r11+10h], rbx
0x180006af7  push    rdi
0x180006af8  sub     rsp, 50h
0x180006afc  mov     rax, cs:__security_cookie
0x180006b03  xor     rax, rsp
0x180006b06  mov     [rsp+58h+var_10], rax
0x180006b0b  mov     eax, [rdx+8]
0x180006b0e  lea     r9, [r11-28h]
0x180006b12  movsd   xmm0, qword ptr [rdx]
0x180006b16  mov     rdi, r8
0x180006b19  mov     rcx, [rcx+0D8h]
0x180006b20  lea     r8, IID_IAggregate
0x180006b27  mov     [rsp+58h+var_18], eax
0x180006b2b  lea     rdx, [r11-20h]
0x180006b2f  movsd   [rsp+58h+var_20], xmm0
0x180006b35  mov     qword ptr [r11-28h], 0
0x180006b3d  mov     rax, [rcx]
0x180006b40  mov     rax, [rax+0C8h]
0x180006b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4c  mov     ebx, eax
0x180006b4e  cmp     eax, 80070490h
0x180006b53  jnz     short loc_180006B59
0x180006b55  xor     eax, eax
0x180006b57  jmp     short loc_180006B7D
0x180006b59  test    eax, eax
0x180006b5b  jns     short loc_180006B78
0x180006b5d  mov     r9d, 934h
0x180006b63  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180006b6a  mov     edx, 1
0x180006b6f  mov     ecx, eax
0x180006b71  call    Log_HREvent
0x180006b76  jmp     short loc_180006B81
0x180006b78  mov     eax, 1
0x180006b7d  mov     [rdi], eax
0x180006b7f  xor     ebx, ebx
0x180006b81  lea     rcx, [rsp+58h+var_28]
0x180006b86  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180006b8b  mov     eax, ebx
0x180006b8d  mov     rcx, [rsp+58h+var_10]
0x180006b92  xor     rcx, rsp; StackCookie
0x180006b95  call    __security_check_cookie
0x180006b9a  mov     rbx, [rsp+58h+arg_8]
0x180006b9f  add     rsp, 50h
0x180006ba3  pop     rdi
0x180006ba4  retn
```
