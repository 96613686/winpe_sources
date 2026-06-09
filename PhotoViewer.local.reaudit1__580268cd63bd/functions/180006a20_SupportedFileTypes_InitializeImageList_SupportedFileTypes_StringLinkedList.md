# SupportedFileTypes::InitializeImageList(SupportedFileTypes::StringLinkedList *)

- ea: `0x180006a20`
- end: `0x180006be9`
- name: `?InitializeImageList@SupportedFileTypes@@AEAAJPEAVStringLinkedList@1@@Z`
- size: `457`
- prototype: `int(SupportedFileTypes *__hidden this, struct SupportedFileTypes::StringLinkedList *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180072504`

## callees

- `0x180006a20`
- `0x180006bf0`
- `0x180080010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180006b88`
- `KERNEL32!LocalFree` at `0x180006b88`
- `KERNEL32!LocalAlloc` at `0x180006b49`
- `KERNEL32!LocalAlloc` at `0x180006b49`
- `ole32!CoCreateInstance` at `0x180006a5c`
- `ole32!CoCreateInstance` at `0x180006a5c`

## pseudocode

```c
__int64 __fastcall SupportedFileTypes::InitializeImageList(
        SupportedFileTypes *this,
        struct SupportedFileTypes::StringLinkedList *a2)
{
  HRESULT Extensions; // ebx
  unsigned __int64 v4; // rax
  unsigned __int16 *v5; // rax
  unsigned __int16 *v6; // rdi
  __int64 i; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  SupportedFileTypes *v10; // [rsp+60h] [rbp+20h] BYREF
  __int64 v11; // [rsp+70h] [rbp+30h] BYREF
  __int64 v12; // [rsp+78h] [rbp+38h] BYREF

  v10 = this;
  ppv = 0;
  Extensions = CoCreateInstance(&CLSID_WICImagingFactory2, 0, 1u, &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70, &ppv);
  if ( Extensions >= 0 )
  {
    v12 = 0;
    if ( (*(int (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 184LL))(ppv, 1, 0, &v12) >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 40LL))(v12);
      for ( i = 0;
            !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 24LL))(v12, 1, &i)
         && Extensions >= 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)i + 16LL))(i) )
      {
        v11 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))i)(
               i,
               &GUID_d8cd007f_d08f_4191_9bfc_236ea7f0e4b5,
               &v11) >= 0 )
        {
          LODWORD(v10) = 0;
          if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, SupportedFileTypes **))(*(_QWORD *)v11 + 136LL))(
                 v11,
                 0,
                 0,
                 &v10) >= 0 )
          {
            if ( (_DWORD)v10 )
            {
              v4 = 2LL * (unsigned int)v10;
              if ( v4 <= 0xFFFFFFFF )
              {
                v5 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)v4);
                v6 = v5;
                if ( v5 )
                {
                  if ( (*(int (__fastcall **)(__int64, _QWORD, unsigned __int16 *, SupportedFileTypes **))(*(_QWORD *)v11 + 136LL))(
                         v11,
                         (unsigned int)v10,
                         v5,
                         &v10) >= 0 )
                    Extensions = SupportedFileTypes::ExtractExtensions(v6, a2);
                  LocalFree(v6);
                }
                else
                {
                  Extensions = -2147024882;
                }
              }
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)Extensions;
}

```

## disassembly

```asm
0x180006a20  mov     [rsp-18h+arg_8], rbx
0x180006a25  mov     [rsp-18h+arg_0], rcx
0x180006a2a  push    rbp
0x180006a2b  push    rsi
0x180006a2c  push    rdi
0x180006a2d  mov     rbp, rsp
0x180006a30  sub     rsp, 40h
0x180006a34  mov     rsi, rdx
0x180006a37  mov     [rbp+var_8], 0
0x180006a3f  xor     edx, edx; pUnkOuter
0x180006a41  lea     rax, [rbp+var_8]
0x180006a45  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180006a4c  mov     [rsp+40h+ppv], rax; ppv
0x180006a51  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180006a58  lea     r8d, [rdx+1]; dwClsContext
0x180006a5c  call    cs:__imp_CoCreateInstance
0x180006a62  mov     ebx, eax
0x180006a64  test    eax, eax
0x180006a66  js      loc_180006BDA
0x180006a6c  mov     rcx, [rbp+var_8]
0x180006a70  lea     r9, [rbp+arg_18]
0x180006a74  mov     [rbp+arg_18], 0
0x180006a7c  xor     r8d, r8d
0x180006a7f  mov     rdx, [rcx]
0x180006a82  mov     rax, [rdx+0B8h]
0x180006a89  lea     edx, [r8+1]
0x180006a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a92  test    eax, eax
0x180006a94  js      loc_180006BCA
0x180006a9a  mov     rcx, [rbp+arg_18]
0x180006a9e  mov     rax, [rcx]
0x180006aa1  mov     rax, [rax+28h]
0x180006aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aaa  mov     [rbp+var_10], 0
0x180006ab2  mov     rcx, [rbp+arg_18]
0x180006ab6  lea     r8, [rbp+var_10]
0x180006aba  xor     r9d, r9d
0x180006abd  mov     rax, [rcx]
0x180006ac0  lea     edx, [r9+1]
0x180006ac4  mov     rax, [rax+18h]
0x180006ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006acd  test    eax, eax
0x180006acf  jnz     loc_180006BBA
0x180006ad5  test    ebx, ebx
0x180006ad7  js      loc_180006BBA
0x180006add  mov     rcx, [rbp+var_10]
0x180006ae1  lea     r8, [rbp+arg_10]
0x180006ae5  mov     [rbp+arg_10], 0
0x180006aed  lea     rdx, _GUID_d8cd007f_d08f_4191_9bfc_236ea7f0e4b5
0x180006af4  mov     rax, [rcx]
0x180006af7  mov     rax, [rax]
0x180006afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aff  test    eax, eax
0x180006b01  js      loc_180006BA5
0x180006b07  mov     rcx, [rbp+arg_10]
0x180006b0b  lea     r9, [rbp+arg_0]
0x180006b0f  mov     dword ptr [rbp+arg_0], 0
0x180006b16  xor     r8d, r8d
0x180006b19  xor     edx, edx
0x180006b1b  mov     rax, [rcx]
0x180006b1e  mov     rax, [rax+88h]
0x180006b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b2a  test    eax, eax
0x180006b2c  js      short loc_180006B95
0x180006b2e  mov     eax, dword ptr [rbp+arg_0]
0x180006b31  test    eax, eax
0x180006b33  jz      short loc_180006B95
0x180006b35  add     rax, rax
0x180006b38  mov     ecx, 0FFFFFFFFh
0x180006b3d  cmp     rax, rcx
0x180006b40  ja      short loc_180006B95
0x180006b42  mov     edx, eax; uBytes
0x180006b44  mov     ecx, 40h ; '@'; uFlags
0x180006b49  call    cs:__imp_LocalAlloc
0x180006b4f  mov     rdi, rax
0x180006b52  test    rax, rax
0x180006b55  jz      short loc_180006B90
0x180006b57  mov     rcx, [rbp+arg_10]
0x180006b5b  lea     r9, [rbp+arg_0]
0x180006b5f  mov     r8, rdi
0x180006b62  mov     rdx, [rcx]
0x180006b65  mov     rax, [rdx+88h]
0x180006b6c  mov     edx, dword ptr [rbp+arg_0]
0x180006b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b74  test    eax, eax
0x180006b76  js      short loc_180006B85
0x180006b78  mov     rdx, rsi; struct SupportedFileTypes::StringLinkedList *
0x180006b7b  mov     rcx, rdi; unsigned __int16 *
0x180006b7e  call    ?ExtractExtensions@SupportedFileTypes@@CAJPEAGPEAVStringLinkedList@1@@Z; SupportedFileTypes::ExtractExtensions(ushort *,SupportedFileTypes::StringLinkedList *)
0x180006b83  mov     ebx, eax
0x180006b85  mov     rcx, rdi; hMem
0x180006b88  call    cs:__imp_LocalFree
0x180006b8e  jmp     short loc_180006B95
0x180006b90  mov     ebx, 8007000Eh
0x180006b95  mov     rcx, [rbp+arg_10]
0x180006b99  mov     rax, [rcx]
0x180006b9c  mov     rax, [rax+10h]
0x180006ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba5  mov     rcx, [rbp+var_10]
0x180006ba9  mov     rax, [rcx]
0x180006bac  mov     rax, [rax+10h]
0x180006bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bb5  jmp     loc_180006AB2
0x180006bba  mov     rcx, [rbp+arg_18]
0x180006bbe  mov     rax, [rcx]
0x180006bc1  mov     rax, [rax+10h]
0x180006bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bca  mov     rcx, [rbp+var_8]
0x180006bce  mov     rax, [rcx]
0x180006bd1  mov     rax, [rax+10h]
0x180006bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bda  mov     eax, ebx
0x180006bdc  mov     rbx, [rsp+40h+arg_8]
0x180006be1  add     rsp, 40h
0x180006be5  pop     rdi
0x180006be6  pop     rsi
0x180006be7  pop     rbp
0x180006be8  retn
```
