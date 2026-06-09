# PropertyJob::PropertyJob(std::shared_ptr<Container>,ushort const *,JobAttributes,ushort const *)

- ea: `0x1800333e8`
- end: `0x1800334d3`
- name: `??0PropertyJob@@QEAA@V?$shared_ptr@VContainer@@@std@@PEBGW4JobAttributes@@1@Z`
- size: `235`
- prototype: `PropertyJob *__fastcall(PropertyJob *this, _QWORD *, __int64, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180032f2c`

## callees

- `0x18001370c`
- `0x180013c1c`
- `0x180018678`
- `0x18001a6a8`
- `0x18001a8ec`
- `0x1800333e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033480`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180033480`

## string_xrefs

- `0x180033492`: `onecoreuap\base\devices\setup\dsm\service\job.cpp`

## pseudocode

```c
PropertyJob *__fastcall PropertyJob::PropertyJob(
        PropertyJob *this,
        _QWORD *a2,
        __int64 a3,
        int a4,
        unsigned __int16 *a5)
{
  HRESULT Instance; // eax
  std::_Ref_count_base *v8; // rcx
  int ppv; // [rsp+20h] [rbp-48h]
  _QWORD v11[5]; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v11[0] = *a2;
  v11[1] = a2[1];
  *a2 = 0;
  a2[1] = 0;
  Job::Job((__int64)this, v11, 5, 0, a3, a4, a5);
  *(_QWORD *)this = &PropertyJob::`vftable';
  *((_QWORD *)this + 16) = 0;
  Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease((char *)this + 128);
  Instance = CoCreateInstance(
               &GUID_5acb106d_1a06_4fcd_862d_02a74de81835,
               0,
               1u,
               &GUID_5163f90c_0c58_4057_bca6_95aa25acf06e,
               (LPVOID *)this + 16);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C0,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\job.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  if ( !a5 )
    Job::_PopulateDefaultLanguages(this);
  v8 = (std::_Ref_count_base *)a2[1];
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  return this;
}

```

## disassembly

```asm
0x1800333e8  mov     r11, rsp
0x1800333eb  mov     [r11+18h], rbx
0x1800333ef  mov     [r11+10h], rdx
0x1800333f3  mov     [r11+8], rcx
0x1800333f7  push    rbp
0x1800333f8  push    rsi
0x1800333f9  push    rdi
0x1800333fa  sub     rsp, 50h
0x1800333fe  mov     rsi, rdx
0x180033401  mov     rdi, rcx
0x180033404  mov     rax, [rdx]
0x180033407  mov     [r11-28h], rax
0x18003340b  mov     rax, [rdx+8]
0x18003340f  mov     [r11-20h], rax
0x180033413  mov     qword ptr [rdx], 0
0x18003341a  mov     qword ptr [rdx+8], 0
0x180033422  mov     rbp, [rsp+68h+arg_20]
0x18003342a  mov     [r11-38h], rbp
0x18003342e  mov     [r11-40h], r9d
0x180033432  mov     [r11-48h], r8
0x180033436  xor     r9d, r9d
0x180033439  lea     r8d, [r9+5]
0x18003343d  lea     rdx, [r11-28h]
0x180033441  call    ??0Job@@QEAA@V?$shared_ptr@VContainer@@@std@@W4JobType@@W4JobObjectType@@PEBGW4JobAttributes@@3@Z; Job::Job(std::shared_ptr<Container>,JobType,JobObjectType,ushort const *,JobAttributes,ushort const *)
0x180033446  nop
0x180033447  lea     rax, ??_7PropertyJob@@6B@; const PropertyJob::`vftable'
0x18003344e  mov     [rdi], rax
0x180033451  lea     rbx, [rdi+80h]
0x180033458  mov     qword ptr [rbx], 0
0x18003345f  mov     rcx, rbx
0x180033462  call    ?InternalRelease@?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDsmDriverPackageSource>::InternalRelease(void)
0x180033467  mov     qword ptr [rsp+68h+ppv], rbx; int
0x18003346c  lea     r9, _GUID_5163f90c_0c58_4057_bca6_95aa25acf06e; riid
0x180033473  xor     edx, edx; pUnkOuter
0x180033475  lea     r8d, [rdx+1]; dwClsContext
0x180033479  lea     rcx, _GUID_5acb106d_1a06_4fcd_862d_02a74de81835; rclsid
0x180033480  call    cs:__imp_CoCreateInstance
0x180033486  mov     rcx, [rsp+68h]; this
0x18003348b  test    eax, eax
0x18003348d  jns     short loc_1800334A4
0x18003348f  mov     r9d, eax; char *
0x180033492  lea     r8, aOnecoreuapBase_9; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180033499  mov     edx, 3C0h; void *
0x18003349e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800334a4  test    rbp, rbp
0x1800334a7  jnz     short loc_1800334B2
0x1800334a9  mov     rcx, rdi; this
0x1800334ac  call    ?_PopulateDefaultLanguages@Job@@IEAAXXZ; Job::_PopulateDefaultLanguages(void)
0x1800334b1  nop
0x1800334b2  mov     rcx, [rsi+8]; this
0x1800334b6  test    rcx, rcx
0x1800334b9  jz      short loc_1800334C0
0x1800334bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800334c0  mov     rax, rdi
0x1800334c3  mov     rbx, [rsp+68h+arg_10]
0x1800334cb  add     rsp, 50h
0x1800334cf  pop     rdi
0x1800334d0  pop     rsi
0x1800334d1  pop     rbp
0x1800334d2  retn
```
