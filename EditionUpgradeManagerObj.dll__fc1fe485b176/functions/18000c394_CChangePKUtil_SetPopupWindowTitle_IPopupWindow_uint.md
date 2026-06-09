# CChangePKUtil::SetPopupWindowTitle(IPopupWindow *,uint)

- ea: `0x18000c394`
- end: `0x18000c453`
- name: `?SetPopupWindowTitle@CChangePKUtil@@SAJPEAUIPopupWindow@@I@Z`
- size: `191`
- prototype: `__int64 __fastcall(struct IPopupWindow *, __int64, __int64, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c870`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c394`
- `0x180017d2c`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c43b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c43b`

## pseudocode

```c
__int64 __fastcall CChangePKUtil::SetPopupWindowTitle(struct IPopupWindow *a1, __int64 a2, __int64 a3, void *a4)
{
  void *v4; // rdi
  unsigned int v6; // ebx
  int v7; // ecx
  int v8; // eax
  int v9; // eax
  int v11; // [rsp+20h] [rbp-18h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v4 = 0;
  pv = 0;
  if ( !a1 )
  {
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_8:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v7);
    goto LABEL_9;
  }
  v8 = TResourceStringAllocCopyEx<unsigned short *>(*(HMODULE *)&CChangePKUtil::m_hInstance, 45, a3, a4, v11, &pv);
  v6 = v8;
  if ( v8 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    v4 = pv;
    goto LABEL_9;
  }
  v4 = pv;
  v9 = (*(__int64 (__fastcall **)(struct IPopupWindow *, LPVOID))(*(_QWORD *)a1 + 32LL))(a1, pv);
  v6 = v9;
  if ( v9 < 0
    || (v9 = (*(__int64 (__fastcall **)(struct IPopupWindow *, void *, _QWORD))(*(_QWORD *)a1 + 256LL))(a1, v4, 0),
        v6 = v9,
        v9 < 0) )
  {
    v7 = v9;
    goto LABEL_8;
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
  if ( v4 )
    CoTaskMemFree(v4);
  return v6;
}

```

## disassembly

```asm
0x18000c394  mov     [rsp+arg_8], rbx
0x18000c399  mov     [rsp+arg_10], rsi
0x18000c39e  push    rdi
0x18000c39f  sub     rsp, 30h
0x18000c3a3  xor     edi, edi
0x18000c3a5  mov     rsi, rcx
0x18000c3a8  mov     [rsp+38h+pv], rdi
0x18000c3ad  test    rcx, rcx
0x18000c3b0  jnz     short loc_18000C3BB
0x18000c3b2  mov     ebx, 80070057h
0x18000c3b7  mov     ecx, ebx
0x18000c3b9  jmp     short loc_18000C427
0x18000c3bb  mov     rcx, cs:?m_hInstance@CChangePKUtil@@2PEAUHINSTANCE__@@EA; int
0x18000c3c2  lea     rax, [rsp+38h+pv]
0x18000c3c7  mov     edx, 2Dh ; '-'; int
0x18000c3cc  mov     [rsp+38h+Src], rax; Src
0x18000c3d1  call    ??$TResourceStringAllocCopyEx@PEAG@@YAJPEAUHINSTANCE__@@IGP6AJPEAX_KPEAPEAG@Z13@Z; TResourceStringAllocCopyEx<ushort *>(HINSTANCE__ *,uint,ushort,long (*)(void *,unsigned __int64,ushort * *),void *,ushort * *)
0x18000c3d6  mov     ebx, eax
0x18000c3d8  test    eax, eax
0x18000c3da  jns     short loc_18000C3EA
0x18000c3dc  mov     ecx, eax
0x18000c3de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c3e3  mov     rdi, [rsp+38h+pv]
0x18000c3e8  jmp     short loc_18000C42C
0x18000c3ea  mov     rax, [rsi]
0x18000c3ed  mov     rcx, rsi
0x18000c3f0  mov     rdi, [rsp+38h+pv]
0x18000c3f5  mov     rdx, rdi
0x18000c3f8  mov     rax, [rax+20h]
0x18000c3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c401  mov     ebx, eax
0x18000c403  test    eax, eax
0x18000c405  js      short loc_18000C425
0x18000c407  mov     rax, [rsi]
0x18000c40a  xor     r8d, r8d
0x18000c40d  mov     rdx, rdi
0x18000c410  mov     rcx, rsi
0x18000c413  mov     rax, [rax+100h]
0x18000c41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c41f  mov     ebx, eax
0x18000c421  test    eax, eax
0x18000c423  jns     short loc_18000C42C
0x18000c425  mov     ecx, eax
0x18000c427  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c42c  mov     ecx, ebx
0x18000c42e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c433  test    rdi, rdi
0x18000c436  jz      short loc_18000C441
0x18000c438  mov     rcx, rdi; pv
0x18000c43b  call    cs:__imp_CoTaskMemFree
0x18000c441  mov     rsi, [rsp+38h+arg_10]
0x18000c446  mov     eax, ebx
0x18000c448  mov     rbx, [rsp+38h+arg_8]
0x18000c44d  add     rsp, 30h
0x18000c451  pop     rdi
0x18000c452  retn
```
