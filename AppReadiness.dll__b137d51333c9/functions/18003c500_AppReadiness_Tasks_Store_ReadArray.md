# AppReadiness::Tasks::Store::ReadArray

- ea: `0x18003c500`
- end: `0x18003c623`
- name: `AppReadiness::Tasks::Store::ReadArray`
- size: `291`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003c168`
- `0x18003c284`
- `0x18003c3fc`

## callees

- `0x180027a4c`
- `0x18003893c`
- `0x18003c500`
- `0x18003ecb4`
- `0x180079010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003c5d3`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003c5d3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c597`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003c597`

## string_xrefs

- `0x18003c5da`: `onecoreuap\shell\appreadiness\src\tasks\storemetadata.cpp`
- `0x18003c5fc`: `reader->GetLocalName(&localName, nullptr)`
- `0x18003c5ee`: `AppReadiness::Tasks::Store::ReadArray`

## pseudocode

```c
_UNKNOWN **__fastcall AppReadiness::Tasks::Store::ReadArray(__int64 *a1, const WCHAR *a2, __int64 a3)
{
  _UNKNOWN **result; // rax
  bool v7; // di
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  LPCWCH lpString2; // [rsp+30h] [rbp-68h] BYREF
  __int64 *v12; // [rsp+38h] [rbp-60h] BYREF
  _BYTE pExceptionObject[88]; // [rsp+40h] [rbp-58h] BYREF
  _UNKNOWN *retaddr; // [rsp+98h] [rbp+0h] BYREF
  int v15; // [rsp+B8h] [rbp+20h] BYREF

  result = &retaddr;
  v15 = 0;
  v7 = 0;
  while ( !v7 )
  {
    result = (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64 *, int *))(*a1 + 48))(a1, &v15);
    if ( (_DWORD)result )
      break;
    if ( v15 == 1 )
    {
      v8 = *a1;
      lpString2 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, LPCWCH *, _QWORD))(v8 + 112))(a1, &lpString2, 0);
      if ( v9 < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          v9,
          "reader->GetLocalName(&localName, nullptr)",
          "AppReadiness::Tasks::Store::ReadArray",
          "onecoreuap\\shell\\appreadiness\\src\\tasks\\storemetadata.cpp",
          375);
        throw (Windows::HResultException *)pExceptionObject;
      }
      if ( CompareStringOrdinal(a2, -1, lpString2, -1, 1) == 2 )
      {
        v10 = *(_QWORD *)(a3 + 56);
        v12 = a1;
        if ( !v10 )
        {
          std::_Xbad_function_call();
          __debugbreak();
        }
        result = (_UNKNOWN **)(*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v10 + 16LL))(v10, &v12);
      }
      else
      {
        result = (_UNKNOWN **)AppReadiness::Tasks::Store::Skip(a1);
      }
    }
    else
    {
      v7 = v15 == 15;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003c500  mov     rax, rsp
0x18003c503  push    rbx
0x18003c504  push    rbp
0x18003c505  push    rsi
0x18003c506  push    rdi
0x18003c507  sub     rsp, 78h
0x18003c50b  mov     rsi, r8
0x18003c50e  mov     dword ptr [rax+20h], 0
0x18003c515  mov     rbp, rdx
0x18003c518  mov     rbx, rcx
0x18003c51b  xor     dil, dil
0x18003c51e  test    dil, dil
0x18003c521  jnz     loc_18003C61A
0x18003c527  mov     rax, [rbx]
0x18003c52a  lea     rdx, [rsp+98h+arg_18]
0x18003c532  mov     rcx, rbx
0x18003c535  mov     rax, [rax+30h]
0x18003c539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c53e  test    eax, eax
0x18003c540  jnz     loc_18003C61A
0x18003c546  mov     ecx, [rsp+98h+arg_18]
0x18003c54d  sub     ecx, 1
0x18003c550  jz      short loc_18003C55C
0x18003c552  cmp     ecx, 0Eh
0x18003c555  jnz     short loc_18003C51E
0x18003c557  mov     dil, 1
0x18003c55a  jmp     short loc_18003C51E
0x18003c55c  mov     rax, [rbx]
0x18003c55f  lea     rdx, [rsp+98h+lpString2]
0x18003c564  xor     r8d, r8d
0x18003c567  mov     [rsp+98h+lpString2], 0
0x18003c570  mov     rcx, rbx
0x18003c573  mov     rax, [rax+70h]
0x18003c577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c57c  test    eax, eax
0x18003c57e  js      short loc_18003C5DA
0x18003c580  mov     r8, [rsp+98h+lpString2]; lpString2
0x18003c585  or      r9d, 0FFFFFFFFh; cchCount2
0x18003c589  or      edx, r9d; cchCount1
0x18003c58c  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x18003c594  mov     rcx, rbp; lpString1
0x18003c597  call    cs:__imp_CompareStringOrdinal
0x18003c59d  cmp     eax, 2
0x18003c5a0  jnz     short loc_18003C5C6
0x18003c5a2  mov     rcx, [rsi+38h]
0x18003c5a6  mov     [rsp+98h+var_60], rbx
0x18003c5ab  test    rcx, rcx
0x18003c5ae  jz      short loc_18003C5D3
0x18003c5b0  mov     rax, [rcx]
0x18003c5b3  lea     rdx, [rsp+98h+var_60]
0x18003c5b8  mov     rax, [rax+10h]
0x18003c5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5c1  jmp     loc_18003C51E
0x18003c5c6  mov     rcx, rbx
0x18003c5c9  call    AppReadiness__Tasks__Store__Skip
0x18003c5ce  jmp     loc_18003C51E
0x18003c5d3  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18003c5d9  int     3; Trap to Debugger
0x18003c5da  lea     rcx, aOnecoreuapShel_37; "onecoreuap\\shell\\appreadiness\\src\\t"...
0x18003c5e1  mov     [rsp+98h+var_70], 177h; int
0x18003c5e9  mov     qword ptr [rsp+98h+bIgnoreCase], rcx; char *
0x18003c5ee  lea     r9, aAppreadinessTa_32; "AppReadiness::Tasks::Store::ReadArray"
0x18003c5f5  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18003c5fa  mov     edx, eax; int
0x18003c5fc  lea     r8, aReaderGetlocal; "reader->GetLocalName(&localName, nullpt"...
0x18003c603  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18003c608  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18003c60f  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18003c614  call    _CxxThrowException_0
0x18003c61a  add     rsp, 78h
0x18003c61e  pop     rdi
0x18003c61f  pop     rsi
0x18003c620  pop     rbp
0x18003c621  pop     rbx
0x18003c622  retn
```
