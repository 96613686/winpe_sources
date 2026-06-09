# CItemIDFactory<DELEGATEBASEITEM,597942229>::s_CreateItemID(DELEGATEBASEITEM const *,IPropertyStore *,_ITEMID_CHILD * *,IMalloc *)

- ea: `0x180046d30`
- end: `0x180046e6c`
- name: `?s_CreateItemID@?$CItemIDFactory@UDELEGATEBASEITEM@@$0CDKDNPNF@@@SAJPEFBUDELEGATEBASEITEM@@PEAUIPropertyStore@@PEAPEAU_ITEMID_CHILD@@PEAUIMalloc@@@Z`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180046370`
- `0x180050590`

## callees

- `0x180046d30`
- `0x180052912`
- `0x18005292a`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046e28`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046e59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046e59`

## pseudocode

```c
__int64 __fastcall CItemIDFactory<DELEGATEBASEITEM,597942229>::s_CreateItemID(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, GUID *, __int64 *),
        __int64 *a3,
        __int64 a4)
{
  unsigned int v4; // eax
  int v7; // ebx
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int16 v10; // di
  void *v11; // rax
  unsigned int Size; // [rsp+50h] [rbp+30h] BYREF
  int Size_4; // [rsp+54h] [rbp+34h]
  __int64 v15; // [rsp+58h] [rbp+38h] BYREF
  void *Src; // [rsp+60h] [rbp+40h] BYREF

  Size_4 = HIDWORD(a1);
  v4 = 0;
  *a3 = 0;
  Src = 0;
  Size = 0;
  if ( !a2 )
  {
LABEL_5:
    v8 = v4 + 12 + 2LL;
    if ( a4 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a4 + 24LL))(a4, v4 + 12 + 2LL);
    }
    else
    {
      v10 = v4 + 22;
      if ( (unsigned __int64)(v4 + 12) + 10 > 0x10001 )
        goto LABEL_14;
      v11 = CoTaskMemAlloc(v4 + 12 + 10LL);
      v9 = (__int64)v11;
      if ( v11 )
      {
        memset_0(v11, 0, v8 + 8);
        *(_WORD *)(v9 + 4) = v8;
        *(_WORD *)v9 = v10 - 2;
        goto LABEL_8;
      }
    }
    if ( v9 )
    {
LABEL_8:
      *(_DWORD *)(v9 + 6) = 597942229;
      *(_WORD *)(v9 + 10) = Size;
      *(_WORD *)(v9 + 12) = 4;
      if ( Src )
        memcpy_0((void *)(v9 + 18), Src, Size);
      *a3 = v9;
      v7 = 0;
      goto LABEL_15;
    }
LABEL_14:
    v7 = -2147024882;
LABEL_15:
    CoTaskMemFree(Src);
    return (unsigned int)v7;
  }
  v15 = 0;
  v7 = (**a2)(a2, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, &v15);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, void **, unsigned int *))(*(_QWORD *)v15 + 40LL))(v15, &Src, &Size);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    if ( v7 >= 0 )
    {
      v4 = Size;
      goto LABEL_5;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180046d30  mov     [rsp-28h+Size], rcx
0x180046d35  push    rbp
0x180046d36  push    rbx
0x180046d37  push    rsi
0x180046d38  push    rdi
0x180046d39  push    r14
0x180046d3b  mov     rbp, rsp
0x180046d3e  sub     rsp, 20h
0x180046d42  xor     eax, eax
0x180046d44  mov     qword ptr [r8], 0
0x180046d4b  mov     [rbp+Src], 0
0x180046d53  mov     rdi, r9
0x180046d56  mov     dword ptr [rbp+Size], eax
0x180046d59  mov     r14, r8
0x180046d5c  mov     r10, rdx
0x180046d5f  test    rdx, rdx
0x180046d62  jz      short loc_180046DC0
0x180046d64  mov     [rbp+arg_8], rax
0x180046d68  lea     r8, [rbp+arg_8]
0x180046d6c  mov     rax, [rdx]
0x180046d6f  mov     rcx, r10
0x180046d72  lea     rdx, _GUID_e318ad57_0aa0_450f_aca5_6fab7103d917
0x180046d79  mov     rax, [rax]
0x180046d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046d81  mov     ebx, eax
0x180046d83  test    eax, eax
0x180046d85  js      loc_180046E5F
0x180046d8b  mov     rcx, [rbp+arg_8]
0x180046d8f  lea     r8, [rbp+Size]
0x180046d93  lea     rdx, [rbp+Src]
0x180046d97  mov     rax, [rcx]
0x180046d9a  mov     rax, [rax+28h]
0x180046d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046da3  mov     rcx, [rbp+arg_8]
0x180046da7  mov     ebx, eax
0x180046da9  mov     rax, [rcx]
0x180046dac  mov     rax, [rax+10h]
0x180046db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046db5  test    ebx, ebx
0x180046db7  js      loc_180046E5F
0x180046dbd  mov     eax, dword ptr [rbp+Size]
0x180046dc0  lea     esi, [rax+0Ch]
0x180046dc3  add     rsi, 2
0x180046dc7  test    rdi, rdi
0x180046dca  jz      short loc_180046E18
0x180046dcc  mov     rax, [rdi]
0x180046dcf  mov     rdx, rsi
0x180046dd2  mov     rcx, rdi
0x180046dd5  mov     rax, [rax+18h]
0x180046dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046dde  mov     rbx, rax
0x180046de1  test    rbx, rbx
0x180046de4  jz      short loc_180046E50
0x180046de6  mov     dword ptr [rbx+6], 23A3DFD5h
0x180046ded  movzx   eax, word ptr [rbp+Size]
0x180046df1  mov     [rbx+0Ah], ax
0x180046df5  mov     word ptr [rbx+0Ch], 4
0x180046dfb  mov     rdx, [rbp+Src]; Src
0x180046dff  test    rdx, rdx
0x180046e02  jz      short loc_180046E11
0x180046e04  mov     r8d, dword ptr [rbp+Size]; Size
0x180046e08  lea     rcx, [rbx+12h]; void *
0x180046e0c  call    memcpy_0
0x180046e11  mov     [r14], rbx
0x180046e14  xor     ebx, ebx
0x180046e16  jmp     short loc_180046E55
0x180046e18  lea     rdi, [rsi+8]
0x180046e1c  cmp     rdi, 10001h
0x180046e23  ja      short loc_180046E50
0x180046e25  mov     rcx, rdi; cb
0x180046e28  call    cs:__imp_CoTaskMemAlloc
0x180046e2e  mov     rbx, rax
0x180046e31  test    rax, rax
0x180046e34  jz      short loc_180046DE1
0x180046e36  mov     r8, rdi; Size
0x180046e39  xor     edx, edx; Val
0x180046e3b  mov     rcx, rax; void *
0x180046e3e  call    memset_0
0x180046e43  sub     di, 2
0x180046e47  mov     [rbx+4], si
0x180046e4b  mov     [rbx], di
0x180046e4e  jmp     short loc_180046DE6
0x180046e50  mov     ebx, 8007000Eh
0x180046e55  mov     rcx, [rbp+Src]; pv
0x180046e59  call    cs:__imp_CoTaskMemFree
0x180046e5f  mov     eax, ebx
0x180046e61  add     rsp, 20h
0x180046e65  pop     r14
0x180046e67  pop     rdi
0x180046e68  pop     rsi
0x180046e69  pop     rbx
0x180046e6a  pop     rbp
0x180046e6b  retn
```
