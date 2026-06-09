# SetAccessibilityProperty(HWND__ *,_GUID,ushort const *)

- ea: `0x180009f88`
- end: `0x18000a02f`
- name: `?SetAccessibilityProperty@@YAJPEAUHWND__@@U_GUID@@PEBG@Z`
- size: `167`
- prototype: `__int64 __fastcall(HWND, struct _GUID *__struct_ptr, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000cb30`
- `0x18000cb60`

## callees

- `0x180009f88`
- `0x180014010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180009fca`
- `ole32!CoCreateInstance` at `0x180009fca`

## pseudocode

```c
__int64 __fastcall SetAccessibilityProperty(HWND a1, struct _GUID *a2, const unsigned __int16 *a3)
{
  HRESULT Instance; // ebx
  __int64 v7; // rax
  _OWORD v9[3]; // [rsp+40h] [rbp-38h] BYREF
  __int64 *v10; // [rsp+90h] [rbp+18h] BYREF

  Instance = -2147024809;
  if ( a3 )
  {
    v10 = 0;
    Instance = CoCreateInstance(&CLSID_AccPropServices, 0, 0x15u, &IID_IAccPropServices, (LPVOID *)&v10);
    if ( Instance >= 0 )
    {
      v7 = *v10;
      v9[0] = *a2;
      Instance = (*(__int64 (__fastcall **)(__int64 *, HWND, __int64, _QWORD, _OWORD *, const unsigned __int16 *))(v7 + 56))(
                   v10,
                   a1,
                   4294967292LL,
                   0,
                   v9,
                   a3);
      (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180009f88  mov     r11, rsp
0x180009f8b  push    rbx
0x180009f8c  push    rbp
0x180009f8d  push    rsi
0x180009f8e  push    rdi
0x180009f8f  sub     rsp, 58h
0x180009f93  mov     rdi, r8
0x180009f96  mov     rsi, rdx
0x180009f99  mov     rbp, rcx
0x180009f9c  mov     ebx, 80070057h
0x180009fa1  test    r8, r8
0x180009fa4  jz      short loc_18000A024
0x180009fa6  xor     edx, edx; pUnkOuter
0x180009fa8  mov     qword ptr [r11+18h], 0
0x180009fb0  lea     rax, [r11+18h]
0x180009fb4  lea     r9, IID_IAccPropServices; riid
0x180009fbb  mov     [r11-58h], rax
0x180009fbf  lea     rcx, CLSID_AccPropServices; rclsid
0x180009fc6  lea     r8d, [rdx+15h]; dwClsContext
0x180009fca  call    cs:__imp_CoCreateInstance
0x180009fd0  mov     ebx, eax
0x180009fd2  test    eax, eax
0x180009fd4  js      short loc_18000A024
0x180009fd6  mov     rcx, [rsp+78h+arg_10]
0x180009fde  lea     rdx, [rsp+78h+var_38]
0x180009fe3  movaps  xmm0, xmmword ptr [rsi]
0x180009fe6  xor     r9d, r9d
0x180009fe9  mov     [rsp+78h+var_50], rdi
0x180009fee  mov     r8d, 0FFFFFFFCh
0x180009ff4  mov     [rsp+78h+var_58], rdx
0x180009ff9  mov     rdx, rbp
0x180009ffc  mov     rax, [rcx]
0x180009fff  movdqa  [rsp+78h+var_38], xmm0
0x18000a005  mov     rax, [rax+38h]
0x18000a009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a00e  mov     rcx, [rsp+78h+arg_10]
0x18000a016  mov     ebx, eax
0x18000a018  mov     rax, [rcx]
0x18000a01b  mov     rax, [rax+10h]
0x18000a01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a024  mov     eax, ebx
0x18000a026  add     rsp, 58h
0x18000a02a  pop     rdi
0x18000a02b  pop     rsi
0x18000a02c  pop     rbp
0x18000a02d  pop     rbx
0x18000a02e  retn
```
