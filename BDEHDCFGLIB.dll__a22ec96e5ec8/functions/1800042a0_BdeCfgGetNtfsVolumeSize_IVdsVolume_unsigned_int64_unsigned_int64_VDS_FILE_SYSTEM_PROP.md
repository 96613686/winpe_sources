# BdeCfgGetNtfsVolumeSize(IVdsVolume *,unsigned __int64 *,unsigned __int64 *,_VDS_FILE_SYSTEM_PROP *)

- ea: `0x1800042a0`
- end: `0x1800043fc`
- name: `?BdeCfgGetNtfsVolumeSize@@YAJPEAUIVdsVolume@@PEA_K1PEAU_VDS_FILE_SYSTEM_PROP@@@Z`
- size: `348`
- prototype: `__int64 __fastcall(struct IVdsVolume *, unsigned __int64 *, unsigned __int64 *, struct _VDS_FILE_SYSTEM_PROP *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180002460`
- `0x180005284`

## callees

- `0x1800042a0`
- `0x180012ad8`
- `0x1800135c0`
- `0x180015010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800043dd`
- `ole32!CoTaskMemFree` at `0x1800043dd`

## pseudocode

```c
__int64 __fastcall BdeCfgGetNtfsVolumeSize(
        struct IVdsVolume *a1,
        unsigned __int64 *a2,
        unsigned __int64 *a3,
        struct _VDS_FILE_SYSTEM_PROP *a4)
{
  __int64 v7; // rcx
  int IsHostOsOnRoamableDrive; // ebx
  unsigned __int64 v10; // rcx
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  __int64 v14; // [rsp+20h] [rbp-50h] BYREF
  int v15; // [rsp+28h] [rbp-48h] BYREF
  __int128 v16; // [rsp+30h] [rbp-40h] BYREF
  __int128 v17; // [rsp+40h] [rbp-30h]
  __int128 v18; // [rsp+50h] [rbp-20h]
  LPVOID pv; // [rsp+60h] [rbp-10h]

  pv = 0;
  v7 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  if ( a1 && a2 && a3 )
  {
    IsHostOsOnRoamableDrive = ((__int64 (__fastcall *)(struct IVdsVolume *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
                                a1,
                                &IID_IVdsVolumeMF,
                                &v14);
    if ( IsHostOsOnRoamableDrive >= 0 )
    {
      IsHostOsOnRoamableDrive = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v14 + 24LL))(v14, &v16);
      if ( IsHostOsOnRoamableDrive >= 0 )
      {
        IsHostOsOnRoamableDrive = NgscbIsHostOsOnRoamableDrive(&v15);
        if ( IsHostOsOnRoamableDrive >= 0 )
        {
          if ( (_DWORD)v16 == 4 || v15 )
          {
            v10 = v18 * DWORD2(v18);
            *a2 = *((_QWORD *)&v17 + 1) * DWORD2(v18);
            *a3 = v10;
            if ( a4 )
            {
              v11 = v17;
              *(_OWORD *)&a4->type = v16;
              v12 = v18;
              *(_OWORD *)&a4->volumeId.Data4[4] = v11;
              *(_QWORD *)&v11 = pv;
              *(_OWORD *)&a4->ullAvailableAllocationUnits = v12;
              pv = 0;
              a4->pwszLabel = (LPWSTR)v11;
              v16 = 0;
              v17 = 0;
              v18 = 0;
            }
          }
          else
          {
            IsHostOsOnRoamableDrive = -1063256056;
          }
        }
      }
    }
    v7 = v14;
  }
  else
  {
    IsHostOsOnRoamableDrive = -2147467261;
  }
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v14 = 0;
  }
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)IsHostOsOnRoamableDrive;
}

```

## disassembly

```asm
0x1800042a0  push    rbp
0x1800042a2  push    rbx
0x1800042a3  push    rsi
0x1800042a4  push    rdi
0x1800042a5  push    r14
0x1800042a7  mov     rbp, rsp
0x1800042aa  sub     rsp, 70h
0x1800042ae  mov     rax, cs:__security_cookie
0x1800042b5  xor     rax, rsp
0x1800042b8  mov     [rbp+var_8], rax
0x1800042bc  xorps   xmm0, xmm0
0x1800042bf  xor     eax, eax
0x1800042c1  mov     rdi, r9
0x1800042c4  mov     [rbp+pv], rax
0x1800042c8  mov     r9, rcx
0x1800042cb  mov     r14, r8
0x1800042ce  xor     ecx, ecx
0x1800042d0  mov     rsi, rdx
0x1800042d3  mov     [rbp+var_50], rcx
0x1800042d7  mov     [rbp+var_48], ecx
0x1800042da  movups  [rbp+var_40], xmm0
0x1800042de  movups  [rbp+var_30], xmm0
0x1800042e2  movups  [rbp+var_20], xmm0
0x1800042e6  test    r9, r9
0x1800042e9  jz      loc_1800043B6
0x1800042ef  test    rdx, rdx
0x1800042f2  jz      loc_1800043B6
0x1800042f8  test    r8, r8
0x1800042fb  jz      loc_1800043B6
0x180004301  mov     rax, [r9]
0x180004304  lea     r8, [rbp+var_50]
0x180004308  lea     rdx, IID_IVdsVolumeMF
0x18000430f  mov     rcx, r9
0x180004312  mov     rax, [rax]
0x180004315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000431a  mov     ebx, eax
0x18000431c  test    eax, eax
0x18000431e  js      loc_1800043B0
0x180004324  mov     rcx, [rbp+var_50]
0x180004328  lea     rdx, [rbp+var_40]
0x18000432c  mov     rax, [rcx]
0x18000432f  mov     rax, [rax+18h]
0x180004333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004338  mov     ebx, eax
0x18000433a  test    eax, eax
0x18000433c  js      short loc_1800043B0
0x18000433e  lea     rcx, [rbp+var_48]; int *
0x180004342  call    ?NgscbIsHostOsOnRoamableDrive@@YAJPEAH@Z; NgscbIsHostOsOnRoamableDrive(int *)
0x180004347  mov     ebx, eax
0x180004349  test    eax, eax
0x18000434b  js      short loc_1800043B0
0x18000434d  cmp     dword ptr [rbp+var_40], 4
0x180004351  jz      short loc_180004360
0x180004353  cmp     [rbp+var_48], 0
0x180004357  jnz     short loc_180004360
0x180004359  mov     ebx, 0C0A00008h
0x18000435e  jmp     short loc_1800043B0
0x180004360  mov     ecx, dword ptr [rbp+var_20+8]
0x180004363  mov     eax, ecx
0x180004365  imul    rax, qword ptr [rbp+var_30+8]
0x18000436a  imul    rcx, qword ptr [rbp+var_20]
0x18000436f  mov     [rsi], rax
0x180004372  mov     [r14], rcx
0x180004375  test    rdi, rdi
0x180004378  jz      short loc_1800043B0
0x18000437a  movups  xmm0, [rbp+var_40]
0x18000437e  xor     eax, eax
0x180004380  movups  xmm1, [rbp+var_30]
0x180004384  movups  xmmword ptr [rdi], xmm0
0x180004387  movups  xmm0, [rbp+var_20]
0x18000438b  movups  xmmword ptr [rdi+10h], xmm1
0x18000438f  movsd   xmm1, [rbp+pv]
0x180004394  movups  xmmword ptr [rdi+20h], xmm0
0x180004398  mov     [rbp+pv], rax
0x18000439c  xorps   xmm0, xmm0
0x18000439f  movsd   qword ptr [rdi+30h], xmm1
0x1800043a4  movups  [rbp+var_40], xmm0
0x1800043a8  movups  [rbp+var_30], xmm0
0x1800043ac  movups  [rbp+var_20], xmm0
0x1800043b0  mov     rcx, [rbp+var_50]
0x1800043b4  jmp     short loc_1800043BB
0x1800043b6  mov     ebx, 80004003h
0x1800043bb  test    rcx, rcx
0x1800043be  jz      short loc_1800043D4
0x1800043c0  mov     rax, [rcx]
0x1800043c3  mov     rax, [rax+10h]
0x1800043c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043cc  mov     [rbp+var_50], 0
0x1800043d4  mov     rcx, [rbp+pv]; pv
0x1800043d8  test    rcx, rcx
0x1800043db  jz      short loc_1800043E3
0x1800043dd  call    cs:__imp_CoTaskMemFree
0x1800043e3  mov     eax, ebx
0x1800043e5  mov     rcx, [rbp+var_8]
0x1800043e9  xor     rcx, rsp; StackCookie
0x1800043ec  call    __security_check_cookie
0x1800043f1  add     rsp, 70h
0x1800043f5  pop     r14
0x1800043f7  pop     rdi
0x1800043f8  pop     rsi
0x1800043f9  pop     rbx
0x1800043fa  pop     rbp
0x1800043fb  retn
```
