# _com_issue_errorex(long,IUnknown *,_GUID const &)

- ea: `0x18001044c`
- end: `0x1800104e3`
- name: `?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z`
- size: `151`
- prototype: `void __fastcall __noreturn(int, struct IUnknown *, const struct _GUID *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fc90`

## callees

- `0x18001044c`
- `0x180010608`
- `0x180015010`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x1800104c3`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800104c3`

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
                 &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60),
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
0x18001044c  mov     r11, rsp
0x18001044f  mov     [r11+8], rbx
0x180010453  mov     [r11+18h], r8
0x180010457  push    rdi
0x180010458  sub     rsp, 20h
0x18001045c  mov     r9, rdx
0x18001045f  mov     edi, ecx
0x180010461  xor     edx, edx
0x180010463  mov     [r11+10h], rdx
0x180010467  test    r9, r9
0x18001046a  jz      short loc_1800104DB
0x18001046c  mov     rax, [r9]
0x18001046f  lea     r8, [r11+18h]
0x180010473  mov     [r11+18h], rdx
0x180010477  mov     rcx, r9
0x18001047a  lea     rdx, _GUID_df0b3d60_548f_101b_8e65_08002b2bd119
0x180010481  mov     rax, [rax]
0x180010484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010489  test    eax, eax
0x18001048b  js      short loc_1800104D6
0x18001048d  mov     rcx, [rsp+28h+arg_10]
0x180010492  lea     rdx, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60
0x180010499  mov     rax, [rcx]
0x18001049c  mov     rax, [rax+18h]
0x1800104a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104a5  mov     rcx, [rsp+28h+arg_10]
0x1800104aa  mov     ebx, eax
0x1800104ac  mov     rdx, [rcx]
0x1800104af  mov     rax, [rdx+10h]
0x1800104b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104b8  test    ebx, ebx
0x1800104ba  jnz     short loc_1800104D6
0x1800104bc  lea     rdx, [rsp+28h+pperrinfo]; pperrinfo
0x1800104c1  xor     ecx, ecx; dwReserved
0x1800104c3  call    cs:__imp_GetErrorInfo
0x1800104c9  test    eax, eax
0x1800104cb  jz      short loc_1800104D6
0x1800104cd  xor     edx, edx
0x1800104cf  mov     [rsp+28h+pperrinfo], rdx
0x1800104d4  jmp     short loc_1800104DB
0x1800104d6  mov     rdx, [rsp+28h+pperrinfo]; struct IErrorInfo *
0x1800104db  mov     ecx, edi; int
0x1800104dd  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
