# UtilStringCopyWithAlloc(ushort * *,uint,ushort const *)

- ea: `0x180006730`
- end: `0x180006804`
- name: `?UtilStringCopyWithAlloc@@YAJPEAPEAGIPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(unsigned __int16 **, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005e60`

## callees

- `0x180005c60`
- `0x180006730`
- `0x18000c572`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006796`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006796`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800067e5`

## pseudocode

```c
__int64 __fastcall UtilStringCopyWithAlloc(unsigned __int16 **a1, __int64 a2, const unsigned __int16 *a3)
{
  const unsigned __int16 *v4; // rax
  __int64 v5; // r9
  __int64 v6; // r9
  unsigned __int64 v7; // rdi
  SIZE_T v8; // rsi
  unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  __int64 result; // rax
  unsigned int v12; // edi

  if ( (unsigned int)a2 > 0x7FFFFFFF )
    return 2147942487LL;
  a2 = (unsigned int)a2;
  v4 = L"mshelp://Windows/?id=230d8c47-ee63-47e1-a1f6-a1d38b07dbee";
  v5 = (unsigned int)a2;
  if ( (_DWORD)a2 )
  {
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --a2;
    }
    while ( a2 );
  }
  v6 = v5 - a2;
  if ( !a2 )
    return 2147942487LL;
  v7 = v6 + 1;
  v8 = 2 * (v6 + 1);
  v9 = (unsigned __int16 *)CoTaskMemAlloc(v8);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  memset_0(v9, 0, v8);
  result = StringCchCopyW(v10, v7, L"mshelp://Windows/?id=230d8c47-ee63-47e1-a1f6-a1d38b07dbee");
  v12 = result;
  if ( (int)result < 0 )
  {
    CoTaskMemFree(v10);
    return v12;
  }
  else
  {
    *a1 = v10;
  }
  return result;
}

```

## disassembly

```asm
0x180006730  push    r14
0x180006732  sub     rsp, 20h
0x180006736  mov     r14, rcx
0x180006739  cmp     edx, 7FFFFFFFh
0x18000673f  ja      loc_1800067F6
0x180006745  mov     edx, edx
0x180006747  lea     rax, aMshelpWindowsI; "mshelp://Windows/?id=230d8c47-ee63-47e1"...
0x18000674e  mov     r9d, edx
0x180006751  test    rdx, rdx
0x180006754  jz      short loc_180006766
0x180006756  cmp     word ptr [rax], 0
0x18000675a  jz      short loc_180006766
0x18000675c  add     rax, 2
0x180006760  sub     rdx, 1
0x180006764  jnz     short loc_180006756
0x180006766  xor     eax, eax
0x180006768  sub     r9, rdx
0x18000676b  test    rdx, rdx
0x18000676e  mov     ecx, 80070057h
0x180006773  cmovz   r9, rax
0x180006777  cmovnz  ecx, eax
0x18000677a  jz      short loc_1800067FB
0x18000677c  mov     [rsp+28h+arg_0], rbx
0x180006781  mov     [rsp+28h+arg_8], rsi
0x180006786  mov     [rsp+28h+arg_10], rdi
0x18000678b  lea     rdi, [r9+1]
0x18000678f  lea     rsi, [rdi+rdi]
0x180006793  mov     rcx, rsi; cb
0x180006796  call    cs:__imp_CoTaskMemAlloc
0x18000679c  mov     rbx, rax
0x18000679f  test    rax, rax
0x1800067a2  jz      short loc_1800067EF
0x1800067a4  mov     r8, rsi; Size
0x1800067a7  xor     edx, edx; Val
0x1800067a9  mov     rcx, rax; void *
0x1800067ac  call    memset_0
0x1800067b1  lea     r8, aMshelpWindowsI; "mshelp://Windows/?id=230d8c47-ee63-47e1"...
0x1800067b8  mov     rdx, rdi; unsigned __int64
0x1800067bb  mov     rcx, rbx; unsigned __int16 *
0x1800067be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800067c3  mov     edi, eax
0x1800067c5  test    eax, eax
0x1800067c7  js      short loc_1800067E2
0x1800067c9  mov     [r14], rbx
0x1800067cc  mov     rsi, [rsp+28h+arg_8]
0x1800067d1  mov     rbx, [rsp+28h+arg_0]
0x1800067d6  mov     rdi, [rsp+28h+arg_10]
0x1800067db  add     rsp, 20h
0x1800067df  pop     r14
0x1800067e1  retn
0x1800067e2  mov     rcx, rbx; pv
0x1800067e5  call    cs:__imp_CoTaskMemFree
0x1800067eb  mov     eax, edi
0x1800067ed  jmp     short loc_1800067CC
0x1800067ef  mov     eax, 8007000Eh
0x1800067f4  jmp     short loc_1800067CC
0x1800067f6  mov     ecx, 80070057h
0x1800067fb  mov     eax, ecx
0x1800067fd  add     rsp, 20h
0x180006801  pop     r14
0x180006803  retn
```
