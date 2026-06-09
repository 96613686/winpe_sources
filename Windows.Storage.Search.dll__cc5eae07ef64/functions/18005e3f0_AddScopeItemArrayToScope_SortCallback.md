# AddScopeItemArrayToScope_SortCallback

- ea: `0x18005e3f0`
- end: `0x18005e54a`
- name: `AddScopeItemArrayToScope_SortCallback`
- size: `346`
- prototype: `int __stdcall(void *p1, void *p2, LPARAM lParam)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callees

- `0x18005e3f0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e4fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e50f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e4fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005e50f`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005e4b6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005e4d3`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005e4b6`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18005e4d3`

## pseudocode

```c
__int64 __fastcall AddScopeItemArrayToScope_SortCallback(__int64 *p1, __int64 *p2, LPARAM lParam)
{
  __int64 v3; // rax
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // edi
  HRESULT v8; // eax
  bool v9; // sf
  __int64 v10; // rdx
  HRESULT v11; // eax
  __int64 v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  __int64 v15; // [rsp+28h] [rbp-8h] BYREF
  PWSTR v16; // [rsp+50h] [rbp+20h] BYREF
  PWSTR pszPath; // [rsp+68h] [rbp+38h] BYREF

  v3 = *p1;
  v15 = 0;
  v5 = 0;
  if ( (*(int (__fastcall **)(__int64 *, GUID *, __int64 *))(v3 + 120))(
         p1,
         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
         &v15) >= 0 )
  {
    v6 = *p2;
    v14 = 0;
    if ( (*(int (__fastcall **)(__int64 *, GUID *, __int64 *))(v6 + 120))(
           p2,
           &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
           &v14) >= 0 )
    {
      pszPath = 0;
      if ( (*(int (__fastcall **)(__int64, __int64, PWSTR *))(*(_QWORD *)v15 + 40LL))(v15, 2147844096LL, &pszPath) < 0 )
      {
        v5 = -1;
      }
      else
      {
        v16 = 0;
        if ( (*(int (__fastcall **)(__int64, __int64, PWSTR *))(*(_QWORD *)v14 + 40LL))(v14, 2147844096LL, &v16) < 0 )
        {
          v5 = 1;
        }
        else
        {
          v7 = 0;
          v8 = 0;
          while ( 1 )
          {
            v9 = v8 < 0;
            if ( v8 )
              break;
            v10 = -1;
            do
              ++v10;
            while ( pszPath[v10] );
            v11 = PathCchRemoveFileSpec(pszPath, v10 + 1);
            v12 = -1;
            v7 = v11;
            do
              ++v12;
            while ( v16[v12] );
            v8 = PathCchRemoveFileSpec(v16, v12 + 1);
            if ( v7 )
            {
              if ( v7 < 0 )
                goto LABEL_20;
              v9 = v8 < 0;
              break;
            }
          }
          if ( !v9 && v7 != v8 )
          {
            if ( v7 == 1 )
            {
              v5 = -1;
            }
            else if ( v8 == 1 )
            {
              v5 = 1;
            }
          }
LABEL_20:
          CoTaskMemFree(v16);
        }
        CoTaskMemFree(pszPath);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return v5;
}

```

## disassembly

```asm
0x18005e3f0  mov     [rsp-18h+arg_8], rbx
0x18005e3f5  push    rbp
0x18005e3f6  push    rdi
0x18005e3f7  push    r14
0x18005e3f9  mov     rbp, rsp
0x18005e3fc  sub     rsp, 30h
0x18005e400  mov     rax, [rcx]
0x18005e403  lea     r8, [rbp+var_8]
0x18005e407  mov     rdi, rdx
0x18005e40a  xor     r14d, r14d
0x18005e40d  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18005e414  mov     [rbp+var_8], r14
0x18005e418  mov     ebx, r14d
0x18005e41b  mov     rax, [rax+78h]
0x18005e41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e424  test    eax, eax
0x18005e426  js      loc_18005E53A
0x18005e42c  mov     rax, [rdi]
0x18005e42f  lea     r8, [rbp+var_10]
0x18005e433  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18005e43a  mov     [rbp+var_10], r14
0x18005e43e  mov     rcx, rdi
0x18005e441  mov     rax, [rax+78h]
0x18005e445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e44a  test    eax, eax
0x18005e44c  js      loc_18005E52A
0x18005e452  mov     rcx, [rbp+var_8]
0x18005e456  lea     r8, [rbp+pszPath]
0x18005e45a  mov     [rbp+pszPath], r14
0x18005e45e  mov     edi, 80058000h
0x18005e463  mov     edx, edi
0x18005e465  mov     rax, [rcx]
0x18005e468  mov     rax, [rax+28h]
0x18005e46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e471  test    eax, eax
0x18005e473  js      loc_18005E517
0x18005e479  mov     rcx, [rbp+var_10]
0x18005e47d  lea     r8, [rbp+arg_0]
0x18005e481  mov     [rbp+arg_0], r14
0x18005e485  mov     edx, edi
0x18005e487  mov     rax, [rcx]
0x18005e48a  mov     rax, [rax+28h]
0x18005e48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e493  test    eax, eax
0x18005e495  js      short loc_18005E506
0x18005e497  mov     edi, r14d
0x18005e49a  mov     eax, r14d
0x18005e49d  test    eax, eax
0x18005e49f  jnz     short loc_18005E4E1
0x18005e4a1  mov     rcx, [rbp+pszPath]; pszPath
0x18005e4a5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005e4a9  inc     rdx
0x18005e4ac  cmp     [rcx+rdx*2], r14w
0x18005e4b1  jnz     short loc_18005E4A9
0x18005e4b3  inc     rdx; cchPath
0x18005e4b6  call    cs:__imp_PathCchRemoveFileSpec
0x18005e4bc  mov     rcx, [rbp+arg_0]; pszPath
0x18005e4c0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18005e4c4  mov     edi, eax
0x18005e4c6  inc     rdx
0x18005e4c9  cmp     [rcx+rdx*2], r14w
0x18005e4ce  jnz     short loc_18005E4C6
0x18005e4d0  inc     rdx; cchPath
0x18005e4d3  call    cs:__imp_PathCchRemoveFileSpec
0x18005e4d9  test    edi, edi
0x18005e4db  jz      short loc_18005E49D
0x18005e4dd  js      short loc_18005E4FA
0x18005e4df  test    eax, eax
0x18005e4e1  js      short loc_18005E4FA
0x18005e4e3  cmp     edi, eax
0x18005e4e5  jz      short loc_18005E4FA
0x18005e4e7  mov     ecx, 1
0x18005e4ec  cmp     edi, ecx
0x18005e4ee  jnz     short loc_18005E4F5
0x18005e4f0  or      ebx, 0FFFFFFFFh
0x18005e4f3  jmp     short loc_18005E4FA
0x18005e4f5  cmp     eax, ecx
0x18005e4f7  cmovz   ebx, ecx
0x18005e4fa  mov     rcx, [rbp+arg_0]; pv
0x18005e4fe  call    cs:__imp_CoTaskMemFree
0x18005e504  jmp     short loc_18005E50B
0x18005e506  mov     ebx, 1
0x18005e50b  mov     rcx, [rbp+pszPath]; pv
0x18005e50f  call    cs:__imp_CoTaskMemFree
0x18005e515  jmp     short loc_18005E51A
0x18005e517  or      ebx, 0FFFFFFFFh
0x18005e51a  mov     rcx, [rbp+var_10]
0x18005e51e  mov     rax, [rcx]
0x18005e521  mov     rax, [rax+10h]
0x18005e525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e52a  mov     rcx, [rbp+var_8]
0x18005e52e  mov     rdx, [rcx]
0x18005e531  mov     rax, [rdx+10h]
0x18005e535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e53a  mov     eax, ebx
0x18005e53c  mov     rbx, [rsp+30h+arg_8]
0x18005e541  add     rsp, 30h
0x18005e545  pop     r14
0x18005e547  pop     rdi
0x18005e548  pop     rbp
0x18005e549  retn
```
