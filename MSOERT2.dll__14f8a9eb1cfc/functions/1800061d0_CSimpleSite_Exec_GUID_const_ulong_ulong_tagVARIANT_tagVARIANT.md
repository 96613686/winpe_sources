# CSimpleSite::Exec(_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x1800061d0`
- end: `0x180006247`
- name: `?Exec@CSimpleSite@@UEAAJPEBU_GUID@@KKPEAUtagVARIANT@@1@Z`
- size: `119`
- prototype: `__int64 __fastcall(CSimpleSite *__hidden this, const struct _GUID *, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800015a0`
- `0x1800061d0`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180006227`
- `KERNEL32!GetCurrentThreadId` at `0x180006227`
- `OLEAUT32!__imp_SysFreeString` at `0x180006221`
- `OLEAUT32!__imp_SysFreeString` at `0x180006221`
- `USER32!PostThreadMessageA` at `0x180006239`
- `USER32!PostThreadMessageA` at `0x180006239`

## pseudocode

```c
__int64 __fastcall CSimpleSite::Exec(CSimpleSite *this, const struct _GUID *a2, int a3)
{
  __int64 v4; // rcx
  CHAR *v5; // rax
  OLECHAR *v6; // rcx
  DWORD CurrentThreadId; // eax
  BSTR bstrString[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( a3 == 2315 )
  {
    v4 = *((_QWORD *)this + 2);
    bstrString[0] = 0;
    if ( (*(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v4 + 384LL))(v4, bstrString) >= 0 && bstrString[0] )
    {
      v5 = PszToANSI(0, bstrString[0]);
      v6 = bstrString[0];
      *((_QWORD *)this + 3) = v5;
      SysFreeString(v6);
    }
    CurrentThreadId = GetCurrentThreadId();
    PostThreadMessageA(CurrentThreadId, 0x12u, 0, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x1800061d0  push    rbx
0x1800061d2  sub     rsp, 30h
0x1800061d6  mov     rbx, rcx
0x1800061d9  cmp     r8d, 90Bh
0x1800061e0  jnz     short loc_18000623F
0x1800061e2  mov     rcx, [rcx+10h]
0x1800061e6  lea     rdx, [rsp+38h+bstrString]
0x1800061eb  mov     [rsp+38h+bstrString], 0
0x1800061f4  mov     rax, [rcx]
0x1800061f7  mov     rax, [rax+180h]
0x1800061fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006203  test    eax, eax
0x180006205  js      short loc_180006227
0x180006207  mov     rdx, [rsp+38h+bstrString]; lpWideCharStr
0x18000620c  test    rdx, rdx
0x18000620f  jz      short loc_180006227
0x180006211  xor     ecx, ecx; CodePage
0x180006213  call    PszToANSI
0x180006218  mov     rcx, [rsp+38h+bstrString]; bstrString
0x18000621d  mov     [rbx+18h], rax
0x180006221  call    cs:__imp_SysFreeString
0x180006227  call    cs:__imp_GetCurrentThreadId
0x18000622d  xor     r9d, r9d; lParam
0x180006230  xor     r8d, r8d; wParam
0x180006233  mov     ecx, eax; idThread
0x180006235  lea     edx, [r9+12h]; Msg
0x180006239  call    cs:__imp_PostThreadMessageA
0x18000623f  xor     eax, eax
0x180006241  add     rsp, 30h
0x180006245  pop     rbx
0x180006246  retn
```
