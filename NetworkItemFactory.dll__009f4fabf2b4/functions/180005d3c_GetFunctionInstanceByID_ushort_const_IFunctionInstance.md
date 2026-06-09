# GetFunctionInstanceByID(ushort const *,IFunctionInstance * *)

- ea: `0x180005d3c`
- end: `0x180005f6b`
- name: `?GetFunctionInstanceByID@@YAJPEBGPEAPEAUIFunctionInstance@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IFunctionInstance **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003400`

## callees

- `0x180005d3c`
- `0x1800070c8`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005e06`
- `KERNEL32!GetLastError` at `0x180005e06`
- `KERNEL32!WaitForSingleObject` at `0x180005ee5`
- `KERNEL32!WaitForSingleObject` at `0x180005ee5`
- `KERNEL32!CreateEventW` at `0x180005df7`
- `KERNEL32!CreateEventW` at `0x180005df7`
- `ole32!CoCreateInstance` at `0x180005d83`
- `ole32!CoCreateInstance` at `0x180005e42`
- `ole32!CoCreateInstance` at `0x180005d83`
- `ole32!CoCreateInstance` at `0x180005e42`

## pseudocode

```c
__int64 __fastcall GetFunctionInstanceByID(const unsigned __int16 *a1, struct IFunctionInstance **a2)
{
  int Instance; // ebx
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax
  int v9; // eax
  _DWORD *v11; // [rsp+68h] [rbp+38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF

  *a2 = 0;
  ppv = 0;
  Instance = CoCreateInstance(
               &GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc,
               0,
               0x401u,
               &GUID_4df99b70_e148_4432_b004_4c9eeb535a5e,
               &ppv);
  if ( Instance >= 0 )
  {
    v5 = operator new(0x38u);
    v11 = v5;
    v6 = v5;
    if ( v5 )
    {
      v5[2] = 1;
      *(_QWORD *)v5 = &CFDNotification::`vftable';
      *((_QWORD *)v5 + 2) = 0;
      v5[6] = -2147467259;
      *((_QWORD *)v5 + 4) = 0;
      v5[10] = 0;
      *((_QWORD *)v5 + 6) = 0;
      EventW = CreateEventW(0, 0, 0, 0);
      *((_QWORD *)v6 + 2) = EventW;
      if ( EventW )
        goto LABEL_7;
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
      if ( Instance >= 0 )
      {
LABEL_7:
        Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     0x401u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)v6 + 6);
        if ( Instance >= 0 )
        {
          v12 = 0;
          Instance = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, _DWORD *, _QWORD, __int64 *))(*(_QWORD *)ppv + 48LL))(
                       ppv,
                       a1,
                       v6,
                       0,
                       &v12);
          if ( Instance >= 0 )
          {
            v11 = 0;
            v9 = (*(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)v12 + 24LL))(v12, &v11);
            Instance = v9;
            if ( v9 < 0 )
            {
              if ( v9 == -2147483638 )
              {
                if ( WaitForSingleObject(*((HANDLE *)v6 + 2), 0xEA60u) )
                {
                  Instance = -2147417835;
                }
                else
                {
                  *a2 = 0;
                  Instance = v6[6];
                  if ( Instance >= 0 )
                    Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, struct IFunctionInstance **))(**((_QWORD **)v6 + 6) + 40LL))(
                                 *((_QWORD *)v6 + 6),
                                 (unsigned int)v6[10],
                                 &GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9,
                                 a2);
                }
              }
            }
            else
            {
              Instance = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, struct IFunctionInstance **))v11)(
                           v11,
                           &GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9,
                           a2);
              (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 16LL))(v11);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
          }
        }
      }
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    else
    {
      Instance = -2147024882;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180005d3c  mov     [rsp-28h+arg_0], rbx
0x180005d41  push    rbp
0x180005d42  push    rsi
0x180005d43  push    rdi
0x180005d44  push    r14
0x180005d46  push    r15
0x180005d48  mov     rbp, rsp
0x180005d4b  sub     rsp, 30h
0x180005d4f  mov     rsi, rdx
0x180005d52  mov     qword ptr [rdx], 0
0x180005d59  mov     r15, rcx
0x180005d5c  mov     [rbp+arg_18], 0
0x180005d64  lea     rax, [rbp+arg_18]
0x180005d68  xor     edx, edx; pUnkOuter
0x180005d6a  lea     rcx, _GUID_c72be2ec_8e90_452c_b29a_ab8ff1c071fc; rclsid
0x180005d71  mov     [rsp+30h+ppv], rax; ppv
0x180005d76  lea     r9, _GUID_4df99b70_e148_4432_b004_4c9eeb535a5e; riid
0x180005d7d  mov     r8d, 401h; dwClsContext
0x180005d83  call    cs:__imp_CoCreateInstance
0x180005d89  mov     ebx, eax
0x180005d8b  test    eax, eax
0x180005d8d  js      loc_180005F58
0x180005d93  mov     ecx, 38h ; '8'; unsigned __int64
0x180005d98  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005d9d  mov     [rbp+arg_8], rax
0x180005da1  mov     rdi, rax
0x180005da4  test    rax, rax
0x180005da7  jz      loc_180005F43
0x180005dad  mov     dword ptr [rdi+8], 1
0x180005db4  lea     rax, ??_7CFDNotification@@6B@; const CFDNotification::`vftable'
0x180005dbb  mov     [rdi], rax
0x180005dbe  mov     qword ptr [rdi+10h], 0
0x180005dc6  mov     dword ptr [rdi+18h], 80004005h
0x180005dcd  mov     qword ptr [rdi+20h], 0
0x180005dd5  mov     dword ptr [rdi+28h], 0
0x180005ddc  mov     qword ptr [rdi+30h], 0
0x180005de4  test    rdi, rdi
0x180005de7  jz      loc_180005F43
0x180005ded  xor     r9d, r9d; lpName
0x180005df0  xor     r8d, r8d; bInitialState
0x180005df3  xor     edx, edx; bManualReset
0x180005df5  xor     ecx, ecx; lpEventAttributes
0x180005df7  call    cs:__imp_CreateEventW
0x180005dfd  mov     [rdi+10h], rax
0x180005e01  test    rax, rax
0x180005e04  jnz     short loc_180005E23
0x180005e06  call    cs:__imp_GetLastError
0x180005e0c  mov     ebx, eax
0x180005e0e  test    eax, eax
0x180005e10  jle     short loc_180005E1B
0x180005e12  movzx   ebx, ax
0x180005e15  or      ebx, 80070000h
0x180005e1b  test    ebx, ebx
0x180005e1d  js      loc_180005F32
0x180005e23  lea     r14, [rdi+30h]
0x180005e27  xor     edx, edx; pUnkOuter
0x180005e29  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180005e30  mov     [rsp+30h+ppv], r14; ppv
0x180005e35  mov     r8d, 401h; dwClsContext
0x180005e3b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180005e42  call    cs:__imp_CoCreateInstance
0x180005e48  mov     ebx, eax
0x180005e4a  test    eax, eax
0x180005e4c  js      loc_180005F32
0x180005e52  mov     rcx, [rbp+arg_18]
0x180005e56  lea     rdx, [rbp+arg_10]
0x180005e5a  mov     [rbp+arg_10], 0
0x180005e62  xor     r9d, r9d
0x180005e65  mov     [rsp+30h+ppv], rdx
0x180005e6a  mov     r8, rdi
0x180005e6d  mov     rdx, r15
0x180005e70  mov     rax, [rcx]
0x180005e73  mov     rax, [rax+30h]
0x180005e77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7c  mov     ebx, eax
0x180005e7e  test    eax, eax
0x180005e80  js      loc_180005F32
0x180005e86  mov     rcx, [rbp+arg_10]
0x180005e8a  lea     rdx, [rbp+arg_8]
0x180005e8e  mov     [rbp+arg_8], 0
0x180005e96  mov     rax, [rcx]
0x180005e99  mov     rax, [rax+18h]
0x180005e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea2  mov     ebx, eax
0x180005ea4  test    eax, eax
0x180005ea6  js      short loc_180005ED5
0x180005ea8  mov     rcx, [rbp+arg_8]
0x180005eac  lea     rdx, _GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9
0x180005eb3  mov     r8, rsi
0x180005eb6  mov     rax, [rcx]
0x180005eb9  mov     rax, [rax]
0x180005ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ec1  mov     rcx, [rbp+arg_8]
0x180005ec5  mov     ebx, eax
0x180005ec7  mov     rax, [rcx]
0x180005eca  mov     rax, [rax+10h]
0x180005ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed3  jmp     short loc_180005F22
0x180005ed5  cmp     eax, 8000000Ah
0x180005eda  jnz     short loc_180005F22
0x180005edc  mov     rcx, [rdi+10h]; hHandle
0x180005ee0  mov     edx, 0EA60h; dwMilliseconds
0x180005ee5  call    cs:__imp_WaitForSingleObject
0x180005eeb  test    eax, eax
0x180005eed  jnz     short loc_180005F1D
0x180005eef  mov     qword ptr [rsi], 0
0x180005ef6  mov     ebx, [rdi+18h]
0x180005ef9  test    ebx, ebx
0x180005efb  js      short loc_180005F22
0x180005efd  mov     rcx, [r14]
0x180005f00  lea     r8, _GUID_33591c10_0bed_4f02_b0ab_1530d5533ee9
0x180005f07  mov     edx, [rdi+28h]
0x180005f0a  mov     r9, rsi
0x180005f0d  mov     rax, [rcx]
0x180005f10  mov     rax, [rax+28h]
0x180005f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f19  mov     ebx, eax
0x180005f1b  jmp     short loc_180005F22
0x180005f1d  mov     ebx, 80010115h
0x180005f22  mov     rcx, [rbp+arg_10]
0x180005f26  mov     rax, [rcx]
0x180005f29  mov     rax, [rax+10h]
0x180005f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f32  mov     rax, [rdi]
0x180005f35  mov     rcx, rdi
0x180005f38  mov     rax, [rax+10h]
0x180005f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f41  jmp     short loc_180005F48
0x180005f43  mov     ebx, 8007000Eh
0x180005f48  mov     rcx, [rbp+arg_18]
0x180005f4c  mov     rax, [rcx]
0x180005f4f  mov     rax, [rax+10h]
0x180005f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f58  mov     eax, ebx
0x180005f5a  mov     rbx, [rsp+30h+arg_0]
0x180005f5f  add     rsp, 30h
0x180005f63  pop     r15
0x180005f65  pop     r14
0x180005f67  pop     rdi
0x180005f68  pop     rsi
0x180005f69  pop     rbp
0x180005f6a  retn
```
