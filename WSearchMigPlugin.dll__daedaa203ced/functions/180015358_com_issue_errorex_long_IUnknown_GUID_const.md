# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x180015358`
- end: `0x1800153ef`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `151`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011220`
- `0x1800144e0`
- `0x1800149a0`
- `0x180014bf0`

## callees

- `0x180015358`
- `0x180015540`
- `0x180018010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1800153cf`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800153cf`

## pseudocode

```c
void __fastcall __noreturn _com_issue_errorex(int a1, struct IUnknown *a2, const struct _GUID *a3)
{
  struct IErrorInfo *v5; // rdx
  struct IUnknownVtbl *lpVtbl; // rax
  int v7; // ebx
  IErrorInfo *pperrinfo; // [rsp+38h] [rbp+10h] BYREF
  const struct _GUID *v9; // [rsp+40h] [rbp+18h] BYREF

  v9 = a3;
  v5 = 0;
  pperrinfo = 0;
  if ( a2 )
  {
    lpVtbl = a2->lpVtbl;
    v9 = 0;
    if ( ((int (__fastcall *)(struct IUnknown *, GUID *, const struct _GUID **))lpVtbl->QueryInterface)(
           a2,
           &GUID_df0b3d60_548f_101b_8e65_08002b2bd119,
           &v9) < 0
      || (v7 = (*(__int64 (__fastcall **)(const struct _GUID *, GUID *))(*(_QWORD *)&v9->Data1 + 24LL))(
                 v9,
                 &GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822b),
          (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v9->Data1 + 16LL))(v9),
          v7)
      || !GetErrorInfo(0, &pperrinfo) )
    {
      v5 = pperrinfo;
    }
    else
    {
      v5 = 0;
      pperrinfo = 0;
    }
  }
  _com_raise_error(a1, v5);
}

```

## disassembly

```asm
0x180015358  mov     r11, rsp
0x18001535b  mov     [r11+8], rbx
0x18001535f  mov     [r11+18h], r8
0x180015363  push    rdi
0x180015364  sub     rsp, 20h
0x180015368  mov     r9, rdx
0x18001536b  mov     edi, ecx
0x18001536d  xor     edx, edx
0x18001536f  mov     [r11+10h], rdx
0x180015373  test    r9, r9
0x180015376  jz      short loc_1800153E7
0x180015378  mov     rax, [r9]
0x18001537b  lea     r8, [r11+18h]
0x18001537f  mov     [r11+18h], rdx
0x180015383  mov     rcx, r9
0x180015386  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x18001538d  mov     rax, [rax]
0x180015390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015395  test    eax, eax
0x180015397  js      short loc_1800153E2
0x180015399  mov     rcx, [rsp+28h+arg_10]
0x18001539e  lea     rdx, _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822b
0x1800153a5  mov     rax, [rcx]
0x1800153a8  mov     rax, [rax+18h]
0x1800153ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153b1  mov     rcx, [rsp+28h+arg_10]
0x1800153b6  mov     ebx, eax
0x1800153b8  mov     rdx, [rcx]
0x1800153bb  mov     rax, [rdx+10h]
0x1800153bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153c4  test    ebx, ebx
0x1800153c6  jnz     short loc_1800153E2
0x1800153c8  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x1800153cd  xor     ecx, ecx; dwReserved
0x1800153cf  call    cs:__imp_GetErrorInfo
0x1800153d5  test    eax, eax
0x1800153d7  jz      short loc_1800153E2
0x1800153d9  xor     edx, edx
0x1800153db  mov     [rsp+28h+pperrinfo], rdx
0x1800153e0  jmp     short loc_1800153E7
0x1800153e2  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x1800153e7  mov     ecx, edi; int
0x1800153e9  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
