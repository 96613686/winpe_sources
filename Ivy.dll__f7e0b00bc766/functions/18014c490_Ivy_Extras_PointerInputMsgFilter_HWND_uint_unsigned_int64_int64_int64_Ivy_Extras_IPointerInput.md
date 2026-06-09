# Ivy::Extras::PointerInputMsgFilter(HWND__ *,uint,unsigned __int64,__int64,__int64 *,Ivy::Extras::IPointerInput &)

- ea: `0x18014c490`
- end: `0x18014c8c9`
- name: `?PointerInputMsgFilter@Extras@Ivy@@YA_NPEAUHWND__@@I_K_JPEA_JAEAUIPointerInput@12@@Z`
- size: `1081`
- prototype: `bool __fastcall(Ivy::Extras *__hidden this, HWND, unsigned int, unsigned __int64, __int64, __int64 *, struct Ivy::Extras::IPointerInput *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180164470`

## callees

- `0x180011ac4`
- `0x180011ae8`
- `0x18014c120`
- `0x18014c294`
- `0x18014c490`
- `0x18016c7b0`
- `0x18016eaf0`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18014c4f7`
- `KERNEL32!GetModuleHandleW` at `0x18014c4f7`
- `KERNEL32!GetProcAddress` at `0x18014c50f`
- `KERNEL32!GetProcAddress` at `0x18014c526`
- `KERNEL32!GetProcAddress` at `0x18014c50f`
- `KERNEL32!GetProcAddress` at `0x18014c526`

## string_xrefs

- `0x18014c4f0`: `user32.dll`

## pseudocode

```c
char __fastcall Ivy::Extras::PointerInputMsgFilter(
        Ivy::Extras *this,
        HWND a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        __int64 *a6)
{
  unsigned int v8; // edi
  HWND v9; // r15
  char v10; // bl
  HMODULE ModuleHandleW; // rax
  HMODULE v12; // r15
  unsigned int (*IsMouseInPointerEnabled)(void); // rcx
  __int64 v14; // r9
  _BYTE *v15; // r8
  __int64 v16; // rdx
  int v17; // eax
  __int64 v19; // r8
  _BYTE *v20; // rdx
  __int64 v21; // r9
  _BYTE *v22; // r8
  __int64 v23; // rdx
  unsigned int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // edi
  unsigned int v27; // edi
  bool v28; // al
  unsigned int v29; // r8d
  __int64 v30; // rcx
  unsigned int v31; // [rsp+30h] [rbp-5C8h] BYREF
  HWND hWndTo; // [rsp+38h] [rbp-5C0h]
  _DWORD v33[12]; // [rsp+40h] [rbp-5B8h] BYREF
  _BYTE v34[400]; // [rsp+70h] [rbp-588h] BYREF
  char v35[8]; // [rsp+200h] [rbp-3F8h] BYREF
  int v36; // [rsp+208h] [rbp-3F0h]
  _DWORD v37[218]; // [rsp+258h] [rbp-3A0h]

  v8 = (unsigned int)a2;
  v9 = (HWND)this;
  hWndTo = (HWND)this;
  v10 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !byte_18022FF28 )
  {
    byte_18022FF28 = 1;
    ModuleHandleW = GetModuleHandleW(L"user32.dll");
    v12 = ModuleHandleW;
    if ( ModuleHandleW )
    {
      GetPointerFrameInfo = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                              ModuleHandleW,
                                                                              "GetPointerFrameInfo");
      IsMouseInPointerEnabled = (unsigned int (*)(void))GetProcAddress(v12, "IsMouseInPointerEnabled");
      qword_18022FF18 = (__int64)IsMouseInPointerEnabled;
      v9 = hWndTo;
      goto LABEL_8;
    }
    v9 = hWndTo;
  }
  IsMouseInPointerEnabled = (unsigned int (*)(void))qword_18022FF18;
LABEL_8:
  if ( v8 > 0x208 )
  {
    v24 = v8 - 581;
    if ( v24 )
    {
      v25 = v24 - 1;
      if ( !v25 )
      {
        if ( !GetPointerFrameInfo )
          return v10;
        v31 = 10;
        if ( !(unsigned int)GetPointerFrameInfo((unsigned __int16)a3, &v31, v35) || !v31 )
        {
          sub_180011AE8(508642563, &qword_1801AB2B8);
          sub_180011AC4(508642563, "GetPointerFrameInfo() failed");
        }
        sub_18014C294(hWndTo);
        v14 = v31;
        v15 = v34;
        v16 = (unsigned __int16)a3;
        goto LABEL_19;
      }
      v26 = v25 - 1;
      if ( !v26 )
      {
        if ( !GetPointerFrameInfo )
          return v10;
        v31 = 10;
        if ( !(unsigned int)GetPointerFrameInfo((unsigned __int16)a3, &v31, v35) || !v31 )
        {
          sub_180011AE8(508642562, &qword_1801AB2B8);
          sub_180011AC4(508642562, "GetPointerFrameInfo() failed");
        }
        sub_18014C294(hWndTo);
        v21 = v31;
        v22 = v34;
        v23 = (unsigned __int16)a3;
        goto LABEL_29;
      }
      v27 = v26 - 3;
      if ( v27 && v27 != 89 )
        return v10;
      v19 = 0;
      v20 = 0;
    }
    else
    {
      if ( !GetPointerFrameInfo )
        return v10;
      v31 = 10;
      if ( !(unsigned int)GetPointerFrameInfo((unsigned __int16)a3, &v31, v35) || !v31 )
      {
        sub_180011AE8(508642561, &qword_1801AB2B8);
        sub_180011AC4(508642561, "GetPointerFrameInfo() failed");
      }
      if ( dword_18022FF0C == v36 )
        return v10;
      dword_18022FF0C = v36;
      v28 = 0;
      v29 = 0;
      do
      {
        if ( v29 >= v31 )
          break;
        v30 = 24LL * v29;
        v28 = v37[v30] != 0;
        ++v29;
      }
      while ( !v37[v30] );
      if ( v28 )
        return v10;
      sub_18014C294(v9);
      v19 = v31;
      v20 = v34;
    }
LABEL_25:
    v17 = (*(__int64 (__fastcall **)(__int64 *, _BYTE *, __int64))(*a6 + 16))(a6, v20, v19);
    return v17 == 1;
  }
  switch ( v8 )
  {
    case 0x208u:
      goto LABEL_26;
    case 0x200u:
      if ( IsMouseInPointerEnabled && IsMouseInPointerEnabled() )
        return v10;
      sub_18014C120(512, a3, a4, v33);
      v19 = 1;
      v20 = v33;
      goto LABEL_25;
    case 0x201u:
      goto LABEL_16;
    case 0x202u:
LABEL_26:
      if ( IsMouseInPointerEnabled && IsMouseInPointerEnabled() )
        return v10;
      sub_18014C120(v8, a3, a4, v33);
      v21 = 1;
      v22 = v33;
      v23 = v33[0];
LABEL_29:
      v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, _BYTE *, __int64))(*a6 + 8))(a6, v23, v22, v21);
      return v17 == 1;
  }
  if ( v8 != 516 )
  {
    if ( v8 != 517 )
    {
      if ( v8 != 519 )
        return v10;
      goto LABEL_16;
    }
    goto LABEL_26;
  }
LABEL_16:
  if ( !IsMouseInPointerEnabled || !IsMouseInPointerEnabled() )
  {
    sub_18014C120(v8, a3, a4, v33);
    v14 = 1;
    v15 = v33;
    v16 = v33[0];
LABEL_19:
    v17 = (*(__int64 (__fastcall **)(__int64 *, __int64, _BYTE *, __int64))*a6)(a6, v16, v15, v14);
    return v17 == 1;
  }
  return v10;
}

```

## disassembly

```asm
0x18014c490  mov     [rsp+arg_8], rbx
0x18014c495  push    rdi
0x18014c496  push    r12
0x18014c498  push    r13
0x18014c49a  push    r14
0x18014c49c  push    r15
0x18014c49e  sub     rsp, 5D0h
0x18014c4a5  mov     rax, cs:__security_cookie
0x18014c4ac  xor     rax, rsp
0x18014c4af  mov     [rsp+5F8h+var_38], rax
0x18014c4b7  mov     r13, r9
0x18014c4ba  mov     r12, r8
0x18014c4bd  mov     edi, edx
0x18014c4bf  mov     r15, rcx
0x18014c4c2  mov     [rsp+5F8h+hWndTo], rcx
0x18014c4c7  mov     rax, [rsp+5F8h+arg_20]
0x18014c4cf  mov     r14, [rsp+5F8h+arg_28]
0x18014c4d7  xor     ebx, ebx
0x18014c4d9  test    rax, rax
0x18014c4dc  jz      short loc_18014C4E1
0x18014c4de  mov     [rax], rbx
0x18014c4e1  cmp     cs:byte_18022FF28, bl
0x18014c4e7  jnz     short loc_18014C542
0x18014c4e9  mov     cs:byte_18022FF28, 1
0x18014c4f0  lea     rcx, ModuleName; "user32.dll"
0x18014c4f7  call    cs:GetModuleHandleW
0x18014c4fd  mov     r15, rax
0x18014c500  test    rax, rax
0x18014c503  jz      short loc_18014C53D
0x18014c505  lea     rdx, ProcName; "GetPointerFrameInfo"
0x18014c50c  mov     rcx, rax; hModule
0x18014c50f  call    cs:GetProcAddress
0x18014c515  mov     cs:GetPointerFrameInfo, rax
0x18014c51c  lea     rdx, aIsmouseinpoint; "IsMouseInPointerEnabled"
0x18014c523  mov     rcx, r15; hModule
0x18014c526  call    cs:GetProcAddress
0x18014c52c  mov     rcx, rax
0x18014c52f  mov     cs:qword_18022FF18, rax
0x18014c536  mov     r15, [rsp+5F8h+hWndTo]
0x18014c53b  jmp     short loc_18014C549
0x18014c53d  mov     r15, [rsp+5F8h+hWndTo]
0x18014c542  mov     rcx, cs:qword_18022FF18
0x18014c549  mov     eax, 208h
0x18014c54e  cmp     edi, eax
0x18014c550  ja      loc_18014C68A
0x18014c556  jz      loc_18014C647
0x18014c55c  mov     eax, edi
0x18014c55e  mov     r15d, 200h
0x18014c564  sub     eax, r15d
0x18014c567  jz      loc_18014C605
0x18014c56d  sub     eax, 1
0x18014c570  jz      short loc_18014C58E
0x18014c572  sub     eax, 1
0x18014c575  jz      loc_18014C647
0x18014c57b  sub     eax, 2
0x18014c57e  jz      short loc_18014C58E
0x18014c580  sub     eax, 1
0x18014c583  jz      loc_18014C647
0x18014c589  cmp     eax, 2
0x18014c58c  jnz     short loc_18014C5D6
0x18014c58e  test    rcx, rcx
0x18014c591  jz      short loc_18014C5A0
0x18014c593  mov     rax, rcx
0x18014c596  call    cs:__guard_dispatch_icall_fptr
0x18014c59c  test    eax, eax
0x18014c59e  jnz     short loc_18014C5D6
0x18014c5a0  lea     r9, [rsp+5F8h+var_5B8]
0x18014c5a5  mov     r8, r13
0x18014c5a8  mov     rdx, r12
0x18014c5ab  mov     ecx, edi
0x18014c5ad  call    sub_18014C120
0x18014c5b2  mov     r9d, 1
0x18014c5b8  lea     r8, [rsp+5F8h+var_5B8]
0x18014c5bd  mov     edx, [rsp+5F8h+var_5B8]
0x18014c5c1  mov     rax, [r14]
0x18014c5c4  mov     rax, [rax]
0x18014c5c7  mov     rcx, r14
0x18014c5ca  call    cs:__guard_dispatch_icall_fptr
0x18014c5d0  cmp     eax, 1
0x18014c5d3  setz    bl
0x18014c5d6  mov     al, bl
0x18014c5d8  jmp     short loc_18014C5DC
0x18014c5da  xor     al, al
0x18014c5dc  mov     rcx, [rsp+5F8h+var_38]
0x18014c5e4  xor     rcx, rsp; StackCookie
0x18014c5e7  call    __security_check_cookie
0x18014c5ec  mov     rbx, [rsp+5F8h+arg_8]
0x18014c5f4  add     rsp, 5D0h
0x18014c5fb  pop     r15
0x18014c5fd  pop     r14
0x18014c5ff  pop     r13
0x18014c601  pop     r12
0x18014c603  pop     rdi
0x18014c604  retn
0x18014c605  test    rcx, rcx
0x18014c608  jz      short loc_18014C617
0x18014c60a  mov     rax, rcx
0x18014c60d  call    cs:__guard_dispatch_icall_fptr
0x18014c613  test    eax, eax
0x18014c615  jnz     short loc_18014C5D6
0x18014c617  lea     r9, [rsp+5F8h+var_5B8]
0x18014c61c  mov     r8, r13
0x18014c61f  mov     rdx, r12
0x18014c622  mov     ecx, r15d
0x18014c625  call    sub_18014C120
0x18014c62a  mov     r8d, 1
0x18014c630  lea     rdx, [rsp+5F8h+var_5B8]
0x18014c635  mov     rax, [r14]
0x18014c638  mov     rcx, r14
0x18014c63b  mov     rax, [rax+10h]
0x18014c63f  call    cs:__guard_dispatch_icall_fptr
0x18014c645  jmp     short loc_18014C5D0
0x18014c647  test    rcx, rcx
0x18014c64a  jz      short loc_18014C65D
0x18014c64c  mov     rax, rcx
0x18014c64f  call    cs:__guard_dispatch_icall_fptr
0x18014c655  test    eax, eax
0x18014c657  jnz     loc_18014C5D6
0x18014c65d  lea     r9, [rsp+5F8h+var_5B8]
0x18014c662  mov     r8, r13
0x18014c665  mov     rdx, r12
0x18014c668  mov     ecx, edi
0x18014c66a  call    sub_18014C120
0x18014c66f  mov     r9d, 1
0x18014c675  lea     r8, [rsp+5F8h+var_5B8]
0x18014c67a  mov     edx, [rsp+5F8h+var_5B8]
0x18014c67e  mov     rax, [r14]
0x18014c681  mov     rax, [rax+8]
0x18014c685  jmp     loc_18014C5C7
0x18014c68a  sub     edi, 245h
0x18014c690  jz      loc_18014C7AC
0x18014c696  sub     edi, 1
0x18014c699  jz      loc_18014C734
0x18014c69f  sub     edi, 1
0x18014c6a2  jz      short loc_18014C6BC
0x18014c6a4  sub     edi, 3
0x18014c6a7  jz      short loc_18014C6B2
0x18014c6a9  cmp     edi, 59h ; 'Y'
0x18014c6ac  jnz     loc_18014C5D6
0x18014c6b2  xor     r8d, r8d
0x18014c6b5  xor     edx, edx
0x18014c6b7  jmp     loc_18014C635
0x18014c6bc  mov     rax, cs:GetPointerFrameInfo
0x18014c6c3  test    rax, rax
0x18014c6c6  jz      loc_18014C5D6
0x18014c6cc  mov     edi, 0Ah
0x18014c6d1  mov     [rsp+5F8h+var_5C8], edi
0x18014c6d5  movzx   r15d, r12w
0x18014c6d9  lea     r8, [rsp+5F8h+var_3F8]
0x18014c6e1  lea     rdx, [rsp+5F8h+var_5C8]
0x18014c6e6  mov     ecx, r15d
0x18014c6e9  call    cs:__guard_dispatch_icall_fptr
0x18014c6ef  test    eax, eax
0x18014c6f1  jz      loc_18014C885
0x18014c6f7  mov     eax, [rsp+5F8h+var_5C8]
0x18014c6fb  test    eax, eax
0x18014c6fd  jz      loc_18014C885
0x18014c703  cmp     eax, edi
0x18014c705  cmovb   edi, eax
0x18014c708  mov     r9d, edi
0x18014c70b  lea     r8, [rsp+5F8h+var_588]
0x18014c710  lea     rdx, [rsp+5F8h+var_3F8]
0x18014c718  mov     rcx, [rsp+5F8h+hWndTo]; hWndTo
0x18014c71d  call    sub_18014C294
0x18014c722  mov     r9d, [rsp+5F8h+var_5C8]
0x18014c727  lea     r8, [rsp+5F8h+var_588]
0x18014c72c  mov     edx, r15d
0x18014c72f  jmp     loc_18014C67E
0x18014c734  mov     rax, cs:GetPointerFrameInfo
0x18014c73b  test    rax, rax
0x18014c73e  jz      loc_18014C5D6
0x18014c744  mov     edi, 0Ah
0x18014c749  mov     [rsp+5F8h+var_5C8], edi
0x18014c74d  movzx   r15d, r12w
0x18014c751  lea     r8, [rsp+5F8h+var_3F8]
0x18014c759  lea     rdx, [rsp+5F8h+var_5C8]
0x18014c75e  mov     ecx, r15d
0x18014c761  call    cs:__guard_dispatch_icall_fptr
0x18014c767  test    eax, eax
0x18014c769  jz      loc_18014C8A6
0x18014c76f  mov     eax, [rsp+5F8h+var_5C8]
0x18014c773  test    eax, eax
0x18014c775  jz      loc_18014C8A6
0x18014c77b  cmp     eax, edi
0x18014c77d  cmovb   edi, eax
0x18014c780  mov     r9d, edi
0x18014c783  lea     r8, [rsp+5F8h+var_588]
0x18014c788  lea     rdx, [rsp+5F8h+var_3F8]
0x18014c790  mov     rcx, [rsp+5F8h+hWndTo]; hWndTo
0x18014c795  call    sub_18014C294
0x18014c79a  mov     r9d, [rsp+5F8h+var_5C8]
0x18014c79f  lea     r8, [rsp+5F8h+var_588]
0x18014c7a4  mov     edx, r15d
0x18014c7a7  jmp     loc_18014C5C1
0x18014c7ac  mov     rax, cs:GetPointerFrameInfo
0x18014c7b3  test    rax, rax
0x18014c7b6  jz      loc_18014C5D6
0x18014c7bc  mov     edi, 0Ah
0x18014c7c1  mov     [rsp+5F8h+var_5C8], edi
0x18014c7c5  movzx   ecx, r12w
0x18014c7c9  lea     r8, [rsp+5F8h+var_3F8]
0x18014c7d1  lea     rdx, [rsp+5F8h+var_5C8]
0x18014c7d6  call    cs:__guard_dispatch_icall_fptr
0x18014c7dc  test    eax, eax
0x18014c7de  jz      loc_18014C864
0x18014c7e4  mov     edx, [rsp+5F8h+var_5C8]
0x18014c7e8  test    edx, edx
0x18014c7ea  jz      short loc_18014C864
0x18014c7ec  mov     eax, [rsp+5F8h+var_3F0]
0x18014c7f3  cmp     cs:dword_18022FF0C, eax
0x18014c7f9  jz      loc_18014C5D6
0x18014c7ff  mov     cs:dword_18022FF0C, eax
0x18014c805  mov     al, bl
0x18014c807  mov     r8d, ebx
0x18014c80a  cmp     r8d, edx
0x18014c80d  jnb     short loc_18014C830
0x18014c80f  mov     eax, r8d
0x18014c812  lea     rcx, [rax+rax*2]
0x18014c816  shl     rcx, 5
0x18014c81a  cmp     [rsp+rcx+5F8h+var_3A0], ebx
0x18014c821  setnz   al
0x18014c824  inc     r8d
0x18014c827  cmp     [rsp+rcx+5F8h+var_3A0], ebx
0x18014c82e  jz      short loc_18014C80A
0x18014c830  test    al, al
0x18014c832  jnz     loc_18014C5D6
0x18014c838  cmp     edx, edi
0x18014c83a  cmovb   edi, edx
0x18014c83d  mov     r9d, edi
0x18014c840  lea     r8, [rsp+5F8h+var_588]
0x18014c845  lea     rdx, [rsp+5F8h+var_3F8]
0x18014c84d  mov     rcx, r15; hWndTo
0x18014c850  call    sub_18014C294
0x18014c855  mov     r8d, [rsp+5F8h+var_5C8]
0x18014c85a  lea     rdx, [rsp+5F8h+var_588]
0x18014c85f  jmp     loc_18014C635
0x18014c864  lea     rdx, qword_1801AB2B8
0x18014c86b  mov     ebx, 1E514501h
0x18014c870  mov     ecx, ebx
0x18014c872  call    sub_180011AE8
0x18014c877  lea     rdx, aGetpointerfram_0; "GetPointerFrameInfo() failed"
0x18014c87e  mov     ecx, ebx
0x18014c880  call    sub_180011AC4
0x18014c885  lea     rdx, qword_1801AB2B8
0x18014c88c  mov     ebx, 1E514502h
0x18014c891  mov     ecx, ebx
0x18014c893  call    sub_180011AE8
0x18014c898  lea     rdx, aGetpointerfram_0; "GetPointerFrameInfo() failed"
0x18014c89f  mov     ecx, ebx
0x18014c8a1  call    sub_180011AC4
0x18014c8a6  lea     rdx, qword_1801AB2B8
0x18014c8ad  mov     ebx, 1E514503h
0x18014c8b2  mov     ecx, ebx
0x18014c8b4  call    sub_180011AE8
0x18014c8b9  lea     rdx, aGetpointerfram_0; "GetPointerFrameInfo() failed"
0x18014c8c0  mov     ecx, ebx
0x18014c8c2  call    sub_180011AC4
```
