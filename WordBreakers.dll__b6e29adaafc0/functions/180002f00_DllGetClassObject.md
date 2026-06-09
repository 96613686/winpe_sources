# DllGetClassObject

- ea: `0x180002f00`
- end: `0x180002ff5`
- name: `DllGetClassObject`
- size: `245`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001e88`
- `0x180002e3c`
- `0x180002f00`
- `0x18000c010`

## string_xrefs

- `0x180002f42`: `DllGetClassObject`
- `0x180002fba`: `DllGetClassObject`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v4; // edi
  _DWORD *v5; // rbx
  int v6; // ecx
  __int64 (*v7)(void); // rax
  int v8; // eax
  int v9; // edx
  int v10; // ecx
  HRESULT; // eax
  __int64 v12; // [rsp+0h] [rbp-48h] BYREF
  _DWORD *v13; // [rsp+68h] [rbp+20h]

  if ( !ppv )
  {
    v4 = -2147024882;
    if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      McTemplateU0sqq_EventWriteTransfer(
        (unsigned int)rclsid,
        (unsigned int)riid,
        (const char *)(unsigned int)"DllGetClassObject",
        50,
        14);
    goto LABEL_12;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v5 = operator new(0x10u);
    if ( v5 )
    {
      *(_QWORD *)v5 = &CClassFactory::`vftable';
      _InterlockedIncrement(&g_dwObjectCount);
      v5[2] = 1;
      g_clsid = (__int128)*rclsid;
    }
    v13 = v5;
    v6 = (int)v5;
    v7 = **(__int64 (***)(void))v5;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
        McTemplateU0sqq_EventWriteTransfer(
          v6,
          (unsigned int)&v12,
          (const char *)(unsigned int)"DllGetClassObject",
          52,
          14);
      v4 = -2147024882;
      v5 = v13;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180002FC8);
LABEL_10:
      if ( v5 )
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
LABEL_12:
       = v4;
    }
  }
  v8 = v7();
  v4 = v8;
  if ( v8 < 0 && (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
    McTemplateU0sqq_EventWriteTransfer(v10, v9, (const char *)(unsigned int)"DllGetClassObject", 54, v8);
  goto LABEL_10;
}

```

## disassembly

```asm
0x180002f00  mov     [rsp+arg_0], rbx
0x180002f05  push    rsi
0x180002f06  push    rdi
0x180002f07  push    r14
0x180002f09  sub     rsp, 30h
0x180002f0d  mov     rdi, r8
0x180002f10  mov     r14, rdx
0x180002f13  mov     rsi, rcx
0x180002f16  mov     [rsp+48h+arg_18], 0
0x180002f1f  test    r8, r8
0x180002f22  jnz     short loc_180002F53
0x180002f24  mov     edi, 8007000Eh
0x180002f29  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180002f30  jz      loc_180002FE5
0x180002f36  mov     [rsp+48h+var_28], 8007000Eh
0x180002f3e  lea     r9d, [r8+32h]
0x180002f42  lea     r8, aDllgetclassobj_0; "DllGetClassObject"
0x180002f49  call    McTemplateU0sqq_EventWriteTransfer
0x180002f4e  jmp     loc_180002FE5
0x180002f53  mov     ecx, 10h; Size
0x180002f58  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002f5d  mov     rbx, rax
0x180002f60  test    rbx, rbx
0x180002f63  jz      short loc_180002F88
0x180002f65  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x180002f6c  mov     [rbx], rax
0x180002f6f  lock inc cs:?g_dwObjectCount@@3JA; long g_dwObjectCount
0x180002f76  mov     dword ptr [rbx+8], 1
0x180002f7d  movups  xmm0, xmmword ptr [rsi]
0x180002f80  movdqu  cs:g_clsid, xmm0
0x180002f88  mov     [rsp+48h+arg_18], rbx
0x180002f8d  mov     rax, [rbx]
0x180002f90  mov     r8, rdi
0x180002f93  mov     rdx, r14
0x180002f96  mov     rcx, rbx
0x180002f99  mov     rax, [rax]
0x180002f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa1  mov     edi, eax
0x180002fa3  test    eax, eax
0x180002fa5  jns     short loc_180002FD1
0x180002fa7  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180002fae  jz      short loc_180002FD1
0x180002fb0  mov     [rsp+48h+var_28], eax
0x180002fb4  mov     r9d, 36h ; '6'
0x180002fba  lea     r8, aDllgetclassobj_0; "DllGetClassObject"
0x180002fc1  call    McTemplateU0sqq_EventWriteTransfer
0x180002fc6  jmp     short loc_180002FD1
0x180002fc8  mov     edi, [rsp+48h+arg_10]
0x180002fcc  mov     rbx, [rsp+48h+arg_18]
0x180002fd1  test    rbx, rbx
0x180002fd4  jz      short loc_180002FE5
0x180002fd6  mov     rax, [rbx]
0x180002fd9  mov     rcx, rbx
0x180002fdc  mov     rax, [rax+10h]
0x180002fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe5  mov     eax, edi
0x180002fe7  mov     rbx, [rsp+48h+arg_0]
0x180002fec  add     rsp, 30h
0x180002ff0  pop     r14
0x180002ff2  pop     rdi
0x180002ff3  pop     rsi
0x180002ff4  retn
```
