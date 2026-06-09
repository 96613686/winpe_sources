# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x14001ff10`
- end: `0x14001ff8f`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14001ff10`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001ff5c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001ff5c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD **v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD **)((char *)this + 64);
  if ( *((_QWORD *)this + 8)
    || (Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)this + 8),
        Instance >= 0) )
  {
    *a2 = (struct IGlobalInterfaceTable *)*v5;
    (*(void (__fastcall **)(_QWORD, _QWORD))(**v5 + 8LL))(*v5, **v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14001ff10  push    rdi
0x14001ff12  sub     rsp, 40h
0x14001ff16  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x14001ff1f  mov     [rsp+48h+arg_0], rbx
0x14001ff24  mov     [rsp+48h+arg_8], rsi
0x14001ff29  mov     rsi, rdx
0x14001ff2c  test    rdx, rdx
0x14001ff2f  jnz     short loc_14001FF38
0x14001ff31  mov     eax, 80004003h
0x14001ff36  jmp     short loc_14001FF7F
0x14001ff38  xor     edi, edi
0x14001ff3a  lea     rbx, [rcx+40h]
0x14001ff3e  cmp     [rbx], rdi
0x14001ff41  jnz     short loc_14001FF68
0x14001ff43  mov     [rsp+48h+ppv], rbx; ppv
0x14001ff48  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x14001ff4f  xor     edx, edx; pUnkOuter
0x14001ff51  lea     r8d, [rdi+1]; dwClsContext
0x14001ff55  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x14001ff5c  call    cs:__imp_CoCreateInstance
0x14001ff62  mov     edi, eax
0x14001ff64  test    eax, eax
0x14001ff66  js      short loc_14001FF7D
0x14001ff68  mov     rcx, [rbx]
0x14001ff6b  mov     [rsi], rcx
0x14001ff6e  mov     rcx, [rbx]
0x14001ff71  mov     rdx, [rcx]
0x14001ff74  mov     rax, [rdx+8]
0x14001ff78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001ff7d  mov     eax, edi
0x14001ff7f  mov     rbx, [rsp+48h+arg_0]
0x14001ff84  mov     rsi, [rsp+48h+arg_8]
0x14001ff89  add     rsp, 40h
0x14001ff8d  pop     rdi
0x14001ff8e  retn
```
