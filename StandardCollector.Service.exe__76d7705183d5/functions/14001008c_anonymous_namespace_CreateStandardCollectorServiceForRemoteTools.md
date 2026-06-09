# _anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools

- ea: `0x14001008c`
- end: `0x1400101f7`
- name: `_anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools`
- size: `363`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x14000356c`

## callees

- `0x14000f9d4`
- `0x14001008c`
- `0x1400137e0`
- `0x140014c70`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1400100e4`
- `ole32!CoCreateInstance` at `0x1400100e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall anonymous_namespace_::CreateStandardCollectorServiceForRemoteTools(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 result; // rax
  HRESULT v5; // ebx
  LPVOID v6; // r9
  __int64 v7; // rcx
  int v8; // eax
  LPVOID ppv; // [rsp+30h] [rbp-20h] BYREF
  __int64 v10; // [rsp+38h] [rbp-18h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h] BYREF

  result = anonymous_namespace_::CreateStandardCollectorServiceForVS(a1, a2, a3, a3);
  if ( !(_DWORD)result )
    return result;
  ppv = 0;
  v5 = CoCreateInstance(
         &GUID_f2dc0f57_0b99_49e3_be80_936dbaa54ee0,
         0,
         4u,
         &GUID_d2020dea_eb40_45d5_b420_b9fb623c4fd1,
         &ppv);
  if ( v5 >= 0 )
  {
    v6 = ppv;
    v7 = 0;
    v10 = 0;
    if ( ppv )
    {
      v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
             ppv,
             &GUID_722e9581_5247_4066_9eda_5d4e36a13de9,
             &v10);
      v6 = ppv;
      if ( v8 >= 0 )
      {
        v7 = v10;
      }
      else
      {
        v7 = 0;
        v10 = 0;
      }
    }
    if ( v7 )
    {
      v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 24LL))(v7, 0);
      if ( v5 < 0 )
      {
LABEL_14:
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
        goto LABEL_16;
      }
      v6 = ppv;
    }
    v11 = 0;
    v5 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)v6 + 24LL))(v6, L"#", &v11);
    if ( v5 >= 0 )
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v11)(
             v11,
             &GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44,
             a3);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    goto LABEL_14;
  }
LABEL_16:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001008c  mov     [rsp-8+arg_0], rbx
0x140010091  mov     [rsp-8+arg_8], rdi
0x140010096  push    rbp
0x140010097  mov     rbp, rsp
0x14001009a  sub     rsp, 50h
0x14001009e  mov     rax, cs:__security_cookie
0x1400100a5  xor     rax, rsp
0x1400100a8  mov     [rbp+var_8], rax
0x1400100ac  mov     rdi, r8
0x1400100af  mov     r9, r8
0x1400100b2  call    _anonymous_namespace___CreateStandardCollectorServiceForVS
0x1400100b7  test    eax, eax
0x1400100b9  jz      loc_1400101DB
0x1400100bf  mov     [rbp+var_20], 0
0x1400100c7  lea     rax, [rbp+var_20]
0x1400100cb  mov     [rsp+50h+ppv], rax; ppv
0x1400100d0  lea     r9, _GUID_d2020dea_eb40_45d5_b420_b9fb623c4fd1; riid
0x1400100d7  xor     edx, edx; pUnkOuter
0x1400100d9  lea     r8d, [rdx+4]; dwClsContext
0x1400100dd  lea     rcx, _GUID_f2dc0f57_0b99_49e3_be80_936dbaa54ee0; rclsid
0x1400100e4  call    cs:__imp_CoCreateInstance
0x1400100ea  mov     ebx, eax
0x1400100ec  test    eax, eax
0x1400100ee  js      loc_1400101C2
0x1400100f4  mov     r9, [rbp+var_20]
0x1400100f8  xor     ecx, ecx
0x1400100fa  mov     [rbp+var_18], rcx
0x1400100fe  test    r9, r9
0x140010101  jz      short loc_140010131
0x140010103  mov     rax, [r9]
0x140010106  lea     r8, [rbp+var_18]
0x14001010a  lea     rdx, _GUID_722e9581_5247_4066_9eda_5d4e36a13de9
0x140010111  mov     rcx, r9
0x140010114  mov     rax, [rax]
0x140010117  call    cs:__guard_dispatch_icall_fptr
0x14001011d  mov     r9, [rbp+var_20]
0x140010121  test    eax, eax
0x140010123  jns     short loc_14001012D
0x140010125  xor     ecx, ecx
0x140010127  mov     [rbp+var_18], rcx
0x14001012b  jmp     short loc_140010131
0x14001012d  mov     rcx, [rbp+var_18]
0x140010131  test    rcx, rcx
0x140010134  jz      short loc_14001014F
0x140010136  mov     rax, [rcx]
0x140010139  xor     edx, edx
0x14001013b  mov     rax, [rax+18h]
0x14001013f  call    cs:__guard_dispatch_icall_fptr
0x140010145  mov     ebx, eax
0x140010147  test    eax, eax
0x140010149  js      short loc_1400101AB
0x14001014b  mov     r9, [rbp+var_20]
0x14001014f  mov     [rbp+var_10], 0
0x140010157  mov     rax, [r9]
0x14001015a  lea     r8, [rbp+var_10]
0x14001015e  lea     rdx, asc_14001A2B0; "#"
0x140010165  mov     rcx, r9
0x140010168  mov     rax, [rax+18h]
0x14001016c  call    cs:__guard_dispatch_icall_fptr
0x140010172  mov     ebx, eax
0x140010174  test    eax, eax
0x140010176  js      short loc_140010194
0x140010178  mov     rcx, [rbp+var_10]
0x14001017c  mov     rax, [rcx]
0x14001017f  mov     r8, rdi
0x140010182  lea     rdx, _GUID_7ae366c7_e696_4178_98d0_dd8d48cd5e44
0x140010189  mov     rax, [rax]
0x14001018c  call    cs:__guard_dispatch_icall_fptr
0x140010192  mov     ebx, eax
0x140010194  mov     rcx, [rbp+var_10]
0x140010198  test    rcx, rcx
0x14001019b  jz      short loc_1400101AB
0x14001019d  mov     rdx, [rcx]
0x1400101a0  mov     rax, [rdx+10h]
0x1400101a4  call    cs:__guard_dispatch_icall_fptr
0x1400101aa  nop
0x1400101ab  mov     rcx, [rbp+var_18]
0x1400101af  test    rcx, rcx
0x1400101b2  jz      short loc_1400101C2
0x1400101b4  mov     rax, [rcx]
0x1400101b7  mov     rax, [rax+10h]
0x1400101bb  call    cs:__guard_dispatch_icall_fptr
0x1400101c1  nop
0x1400101c2  mov     rcx, [rbp+var_20]
0x1400101c6  test    rcx, rcx
0x1400101c9  jz      short loc_1400101D9
0x1400101cb  mov     rax, [rcx]
0x1400101ce  mov     rax, [rax+10h]
0x1400101d2  call    cs:__guard_dispatch_icall_fptr
0x1400101d8  nop
0x1400101d9  mov     eax, ebx
0x1400101db  mov     rcx, [rbp+var_8]
0x1400101df  xor     rcx, rsp; StackCookie
0x1400101e2  call    __security_check_cookie
0x1400101e7  mov     rbx, [rsp+50h+arg_0]
0x1400101ec  mov     rdi, [rsp+50h+arg_8]
0x1400101f1  add     rsp, 50h
0x1400101f5  pop     rbp
0x1400101f6  retn
```
