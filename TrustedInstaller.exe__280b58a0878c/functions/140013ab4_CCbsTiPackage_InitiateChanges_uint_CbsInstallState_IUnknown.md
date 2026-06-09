# CCbsTiPackage::InitiateChanges(uint,_CbsInstallState,IUnknown *)

- ea: `0x140013ab4`
- end: `0x140013b9b`
- name: `?InitiateChanges@CCbsTiPackage@@UEAAJIW4_CbsInstallState@@PEAUIUnknown@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x140013aa0`

## callees

- `0x1400023e0`
- `0x140013ab4`
- `0x140017658`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall CCbsTiPackage::InitiateChanges(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 (__fastcall ***a4)(_QWORD, GUID *, __int64 *))
{
  __int64 v6; // rcx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-38h] BYREF

  v6 = 0;
  v12 = 0;
  if ( *(_QWORD *)(a1 - 16) )
  {
    if ( a4 )
    {
      v8 = (**a4)(a4, &GUID_75207392_23f2_4396_85f0_8fdb879ed0ed, &v12);
      v9 = v8;
      if ( v8 < 0 )
      {
        CBSWdsLogLight(0x4000000u, (unsigned int)v8, (size_t *)1, "TiPackage: Failed to query client UI handler.");
LABEL_5:
        v6 = v12;
        goto LABEL_9;
      }
      v10 = *(_QWORD *)(a1 - 64) + 16LL + *(int *)(*(_QWORD *)(*(_QWORD *)(a1 - 64) + 16LL) + 4LL);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 128LL))(v10, v12);
    }
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(a1 - 16) + 88LL))(
           *(_QWORD *)(a1 - 16),
           a2,
           a3,
           0);
    goto LABEL_5;
  }
  v9 = -2147467263;
LABEL_9:
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v9;
}

```

## disassembly

```asm
0x140013ab4  push    rbx
0x140013ab6  push    rbp
0x140013ab7  push    rsi
0x140013ab8  push    rdi
0x140013ab9  sub     rsp, 48h
0x140013abd  mov     rax, cs:__security_cookie
0x140013ac4  xor     rax, rsp
0x140013ac7  mov     [rsp+68h+var_30], rax
0x140013acc  mov     rdi, rcx
0x140013acf  mov     ebp, r8d
0x140013ad2  xor     ecx, ecx
0x140013ad4  mov     esi, edx
0x140013ad6  mov     [rsp+68h+var_38], rcx
0x140013adb  cmp     [rdi-10h], rcx
0x140013adf  jz      loc_140013B6D
0x140013ae5  test    r9, r9
0x140013ae8  jz      short loc_140013B51
0x140013aea  mov     rax, [r9]
0x140013aed  lea     r8, [rsp+68h+var_38]
0x140013af2  lea     rdx, _GUID_75207392_23f2_4396_85f0_8fdb879ed0ed
0x140013af9  mov     rcx, r9
0x140013afc  mov     rax, [rax]
0x140013aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b04  mov     ebx, eax
0x140013b06  test    eax, eax
0x140013b08  jns     short loc_140013B2A
0x140013b0a  lea     r9, aTipackageFaile; "TiPackage: Failed to query client UI ha"...
0x140013b11  mov     r8d, 1
0x140013b17  mov     edx, eax
0x140013b19  mov     ecx, 4000000h
0x140013b1e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140013b23  mov     rcx, [rsp+68h+var_38]
0x140013b28  jmp     short loc_140013B72
0x140013b2a  mov     rdx, [rdi-40h]
0x140013b2e  mov     rax, [rdx+10h]
0x140013b32  add     rdx, 10h
0x140013b36  movsxd  rcx, dword ptr [rax+4]
0x140013b3a  add     rcx, rdx
0x140013b3d  mov     rdx, [rsp+68h+var_38]
0x140013b42  mov     rax, [rcx]
0x140013b45  mov     rax, [rax+80h]
0x140013b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b51  mov     rcx, [rdi-10h]
0x140013b55  xor     r9d, r9d
0x140013b58  mov     r8d, ebp
0x140013b5b  mov     edx, esi
0x140013b5d  mov     rax, [rcx]
0x140013b60  mov     rax, [rax+58h]
0x140013b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b69  mov     ebx, eax
0x140013b6b  jmp     short loc_140013B23
0x140013b6d  mov     ebx, 80004001h
0x140013b72  test    rcx, rcx
0x140013b75  jz      short loc_140013B83
0x140013b77  mov     rax, [rcx]
0x140013b7a  mov     rax, [rax+10h]
0x140013b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013b83  mov     eax, ebx
0x140013b85  mov     rcx, [rsp+68h+var_30]
0x140013b8a  xor     rcx, rsp; StackCookie
0x140013b8d  call    __security_check_cookie
0x140013b92  add     rsp, 48h
0x140013b96  pop     rdi
0x140013b97  pop     rsi
0x140013b98  pop     rbp
0x140013b99  pop     rbx
0x140013b9a  retn
```
