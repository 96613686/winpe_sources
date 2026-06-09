# MetaBaseGetADsClass(IMSAdminBaseW *,ushort *,IIsSchema *,ushort *,ulong)

- ea: `0x180013fd0`
- end: `0x18001413d`
- name: `?MetaBaseGetADsClass@@YAJPEAUIMSAdminBaseW@@PEAGPEAVIIsSchema@@1K@Z`
- size: `365`
- prototype: `__int64 __fastcall(struct IMSAdminBaseW *, wchar_t *Str, struct IIsSchema *this, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800049c0`
- `0x1800079c4`

## callees

- `0x180012ffc`
- `0x180013fd0`
- `0x18001bc54`
- `0x18001e010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800140e9`
- `msvcrt!wcscpy_s` at `0x180014119`
- `msvcrt!wcscpy_s` at `0x1800140e9`
- `msvcrt!wcscpy_s` at `0x180014119`
- `msvcrt!wcsstr` at `0x1800140aa`
- `msvcrt!wcsstr` at `0x1800140c8`
- `msvcrt!wcsstr` at `0x1800140aa`
- `msvcrt!wcsstr` at `0x1800140c8`
- `msvcrt!_wcsupr` at `0x18001409a`
- `msvcrt!_wcsupr` at `0x18001409a`

## string_xrefs

- `0x1800140b5`: `IIsWebDirectory`

## pseudocode

```c
__int64 __fastcall MetaBaseGetADsClass(
        struct IMSAdminBaseW *a1,
        wchar_t *Str,
        struct IIsSchema *this,
        unsigned __int16 *a4,
        unsigned int a5)
{
  HRESULT (__stdcall *OpenKey)(IMSAdminBaseW *, METADATA_HANDLE, LPCWSTR, DWORD, DWORD, PMETADATA_HANDLE); // rax
  int v10; // ebx
  struct IMSAdminBaseWVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetData)(IMSAdminBaseW *, METADATA_HANDLE, LPCWSTR, PMETADATA_RECORD, DWORD *); // rax
  int v13; // eax
  const wchar_t *v14; // r8
  wchar_t *v15; // rax
  __int128 v17; // [rsp+40h] [rbp-38h] BYREF
  __int128 v18; // [rsp+50h] [rbp-28h]
  __int64 v19; // [rsp+60h] [rbp-18h]
  int v20; // [rsp+B0h] [rbp+38h] BYREF

  a5 = 0;
  v19 = 0;
  v20 = 0;
  OpenKey = a1->lpVtbl->OpenKey;
  v17 = 0;
  v18 = 0;
  v10 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, wchar_t *, __int64, int, unsigned int *))OpenKey)(
          a1,
          0,
          Str,
          1,
          30000,
          &a5);
  if ( v10 >= 0 )
  {
    lpVtbl = a1->lpVtbl;
    LODWORD(v17) = 1002;
    GetData = lpVtbl->GetData;
    HIDWORD(v17) = 2;
    *(_QWORD *)((char *)&v17 + 4) = 1;
    LODWORD(v18) = 520;
    *((_QWORD *)&v18 + 1) = a4;
    v13 = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const OLECHAR *, __int128 *, int *))GetData)(
            a1,
            a5,
            &psz,
            &v17,
            &v20);
    v10 = v13;
    if ( v13 >= 0 )
    {
      v10 = IIsSchema::ValidateClassName(this, a4);
      if ( v10 == -2147463164 )
        wcscpy_s(a4, 0x104u, L"IIsObject");
    }
    else if ( v13 == -2146646015 )
    {
      _wcsupr(Str);
      if ( wcsstr(Str, L"W3SVC") )
      {
        v14 = L"IIsWebDirectory";
      }
      else
      {
        v15 = wcsstr(Str, L"MSFTPSVC");
        v14 = L"IIsFtpVirtualDir";
        if ( !v15 )
          v14 = L"IIsObject";
      }
      wcscpy_s(a4, 0x104u, v14);
      v10 = 1;
    }
  }
  if ( a5 )
    CloseAdminBaseKey(a1, a5);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180013fd0  push    rbp
0x180013fd2  push    rbx
0x180013fd3  push    rsi
0x180013fd4  push    rdi
0x180013fd5  push    r14
0x180013fd7  push    r15
0x180013fd9  mov     rbp, rsp
0x180013fdc  sub     rsp, 78h
0x180013fe0  xor     eax, eax
0x180013fe2  mov     [rbp+arg_20], 0
0x180013fe9  mov     [rbp+var_18], rax
0x180013fed  mov     r14, rcx
0x180013ff0  mov     [rbp+arg_0], eax
0x180013ff3  xorps   xmm0, xmm0
0x180013ff6  mov     rax, [rcx]
0x180013ff9  mov     r15, r8
0x180013ffc  lea     rcx, [rbp+arg_20]
0x180014000  mov     rdi, r9
0x180014003  mov     [rsp+78h+var_50], rcx
0x180014008  mov     rsi, rdx
0x18001400b  mov     r8, rdx
0x18001400e  mov     dword ptr [rsp+78h+var_58], 7530h
0x180014016  mov     rax, [rax+88h]
0x18001401d  mov     r9d, 1
0x180014023  xor     edx, edx
0x180014025  mov     rcx, r14
0x180014028  movups  [rbp+var_38], xmm0
0x18001402c  movups  [rbp+var_28], xmm0
0x180014030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014035  mov     ebx, eax
0x180014037  test    eax, eax
0x180014039  js      loc_18001411F
0x18001403f  mov     rax, [r14]
0x180014042  lea     rcx, [rbp+arg_0]
0x180014046  mov     edx, [rbp+arg_20]
0x180014049  lea     r9, [rbp+var_38]
0x18001404d  mov     [rsp+78h+var_58], rcx
0x180014052  lea     r8, psz
0x180014059  mov     rcx, r14
0x18001405c  mov     dword ptr [rbp+var_38], 3EAh
0x180014063  mov     rax, [rax+50h]
0x180014067  mov     dword ptr [rbp+var_38+0Ch], 2
0x18001406e  mov     qword ptr [rbp+var_38+4], 1
0x180014076  mov     dword ptr [rbp+var_28], 208h
0x18001407d  mov     qword ptr [rbp+var_28+8], rdi
0x180014081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014086  mov     ebx, eax
0x180014088  test    eax, eax
0x18001408a  jns     short loc_1800140F6
0x18001408c  cmp     eax, 800CC801h
0x180014091  jnz     loc_18001411F
0x180014097  mov     rcx, rsi; String
0x18001409a  call    cs:__imp__wcsupr
0x1800140a0  lea     rdx, aW3svc; "W3SVC"
0x1800140a7  mov     rcx, rsi; Str
0x1800140aa  call    cs:__imp_wcsstr
0x1800140b0  test    rax, rax
0x1800140b3  jz      short loc_1800140BE
0x1800140b5  lea     r8, aIiswebdirector_1; "IIsWebDirectory"
0x1800140bc  jmp     short loc_1800140E1
0x1800140be  lea     rdx, aMsftpsvc; "MSFTPSVC"
0x1800140c5  mov     rcx, rsi; Str
0x1800140c8  call    cs:__imp_wcsstr
0x1800140ce  lea     r8, aIisftpvirtuald; "IIsFtpVirtualDir"
0x1800140d5  test    rax, rax
0x1800140d8  jnz     short loc_1800140E1
0x1800140da  lea     r8, aIisobject; "IIsObject"
0x1800140e1  mov     edx, 104h; SizeInWords
0x1800140e6  mov     rcx, rdi; Destination
0x1800140e9  call    cs:__imp_wcscpy_s
0x1800140ef  mov     ebx, 1
0x1800140f4  jmp     short loc_18001411F
0x1800140f6  mov     rdx, rdi; unsigned __int16 *
0x1800140f9  mov     rcx, r15; this
0x1800140fc  call    ?ValidateClassName@IIsSchema@@QEAAJPEBG@Z; IIsSchema::ValidateClassName(ushort const *)
0x180014101  mov     ebx, eax
0x180014103  cmp     eax, 80005004h
0x180014108  jnz     short loc_18001411F
0x18001410a  lea     r8, aIisobject; "IIsObject"
0x180014111  mov     edx, 104h; SizeInWords
0x180014116  mov     rcx, rdi; Destination
0x180014119  call    cs:__imp_wcscpy_s
0x18001411f  mov     edx, [rbp+arg_20]; unsigned int
0x180014122  test    edx, edx
0x180014124  jz      short loc_18001412E
0x180014126  mov     rcx, r14; struct IMSAdminBaseW *
0x180014129  call    ?CloseAdminBaseKey@@YAXPEAUIMSAdminBaseW@@K@Z; CloseAdminBaseKey(IMSAdminBaseW *,ulong)
0x18001412e  mov     eax, ebx
0x180014130  add     rsp, 78h
0x180014134  pop     r15
0x180014136  pop     r14
0x180014138  pop     rdi
0x180014139  pop     rsi
0x18001413a  pop     rbx
0x18001413b  pop     rbp
0x18001413c  retn
```
