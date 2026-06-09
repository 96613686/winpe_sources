# CRPCServiceManager::CRPCServiceManager(ushort const *)

- ea: `0x18001231c`
- end: `0x18001241d`
- name: `??0CRPCServiceManager@@AEAA@PEBG@Z`
- size: `257`
- prototype: `CRPCServiceManager *__fastcall(CRPCServiceManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x1800124bc`

## callees

- `0x180002aa0`
- `0x18001231c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800123ab`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001237b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001237b`

## string_xrefs

- `0x1800123d4`: `appmgmts.dll`

## pseudocode

```c
CRPCServiceManager *__fastcall CRPCServiceManager::CRPCServiceManager(
        CRPCServiceManager *this,
        const unsigned __int16 *a2)
{
  unsigned __int16 *v3; // rax
  int v4; // eax
  int v5; // eax
  unsigned __int16 v6; // di
  CRPCServiceManager *result; // rax

  *((_QWORD *)this + 1) = 87;
  *(_QWORD *)this = &CGPRPCServerBase::`vftable';
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 6) = qword_18002D870;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 14) = 30;
  if ( is_mul_ok(0x25u, 2u) )
  {
    v3 = (unsigned __int16 *)LocalAlloc(0x40u, 0x4Au);
    *((_QWORD *)this + 5) = v3;
    if ( v3 )
    {
      v5 = StringCchCopyW(v3, 0x25u, L"8c7daf44-b6dc-11d1-9a4c-0020af6e7c57");
      v6 = v5;
      if ( v5 >= 0 )
      {
        v4 = 0;
      }
      else
      {
        LocalFree(*((HLOCAL *)this + 5));
        v4 = v6;
        *((_QWORD *)this + 5) = 0;
      }
    }
    else
    {
      v4 = 14;
    }
  }
  else
  {
    v4 = 534;
  }
  *((_DWORD *)this + 2) = v4;
  *(_QWORD *)this = &CRPCServiceManager::`vftable';
  *((_QWORD *)this + 9) = L"appmgmts.dll";
  result = this;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_QWORD *)this + 8) = 0;
  CRPCServiceManager::_pSingletonManager = 0;
  return result;
}

```

## disassembly

```asm
0x18001231c  mov     [rsp+arg_0], rbx
0x180012321  push    rdi
0x180012322  sub     rsp, 20h
0x180012326  lea     rax, ??_7CGPRPCServerBase@@6B@; const CGPRPCServerBase::`vftable'
0x18001232d  mov     qword ptr [rcx+8], 57h ; 'W'
0x180012335  mov     [rcx], rax
0x180012338  mov     edi, 25h ; '%'
0x18001233d  lea     rax, qword_18002D870
0x180012344  mov     dword ptr [rcx+20h], 0
0x18001234b  mov     [rcx+30h], rax
0x18001234f  mov     rbx, rcx
0x180012352  mov     qword ptr [rcx+28h], 0
0x18001235a  lea     eax, [rdi-23h]
0x18001235d  mov     dword ptr [rcx+38h], 1Eh
0x180012364  mul     rdi
0x180012367  mov     [rsp+28h+arg_8], 0
0x180012370  test    rdx, rdx
0x180012373  jnz     short loc_1800123C2
0x180012375  mov     rdx, rax; uBytes
0x180012378  lea     ecx, [rdi+1Bh]; uFlags
0x18001237b  call    cs:__imp_LocalAlloc
0x180012381  mov     [rbx+28h], rax
0x180012385  test    rax, rax
0x180012388  jnz     short loc_18001238F
0x18001238a  lea     eax, [rdi-17h]
0x18001238d  jmp     short loc_1800123C7
0x18001238f  lea     r8, a8c7daf44B6dc11; "8c7daf44-b6dc-11d1-9a4c-0020af6e7c57"
0x180012396  mov     rdx, rdi; unsigned __int64
0x180012399  mov     rcx, rax; unsigned __int16 *
0x18001239c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800123a1  mov     edi, eax
0x1800123a3  test    eax, eax
0x1800123a5  jns     short loc_1800123BE
0x1800123a7  mov     rcx, [rbx+28h]; hMem
0x1800123ab  call    cs:__imp_LocalFree
0x1800123b1  movzx   eax, di
0x1800123b4  mov     qword ptr [rbx+28h], 0
0x1800123bc  jmp     short loc_1800123C7
0x1800123be  xor     eax, eax
0x1800123c0  jmp     short loc_1800123C7
0x1800123c2  mov     eax, 216h
0x1800123c7  mov     [rbx+8], eax
0x1800123ca  lea     rax, ??_7CRPCServiceManager@@6B@; const CRPCServiceManager::`vftable'
0x1800123d1  mov     [rbx], rax
0x1800123d4  lea     rax, aAppmgmtsDll_0; "appmgmts.dll"
0x1800123db  mov     [rbx+48h], rax
0x1800123df  mov     rax, rbx
0x1800123e2  mov     qword ptr [rbx+80h], 0
0x1800123ed  mov     qword ptr [rbx+50h], 0
0x1800123f5  mov     dword ptr [rbx+88h], 0
0x1800123ff  mov     qword ptr [rbx+40h], 0
0x180012407  mov     rbx, [rsp+28h+arg_0]
0x18001240c  mov     cs:?_pSingletonManager@CRPCServiceManager@@0PEAV1@EA, 0; CRPCServiceManager * CRPCServiceManager::_pSingletonManager
0x180012417  add     rsp, 20h
0x18001241b  pop     rdi
0x18001241c  retn
```
