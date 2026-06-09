# _anonymous_namespace_::GetHandlerForExtension

- ea: `0x18002655c`
- end: `0x180026797`
- name: `_anonymous_namespace_::GetHandlerForExtension`
- size: `571`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025c60`
- `0x180026120`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000a4d0`
- `0x18000dc74`
- `0x18002655c`
- `0x180026b10`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800266ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800266ce`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180026606`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180026606`

## string_xrefs

- `0x1800265b8`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\downloadexecutionbroker.cpp`
- `0x180026714`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\downloadexecutionbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::GetHandlerForExtension(__int64 a1, unsigned __int16 **a2, _QWORD *a3)
{
  char v6; // al
  HRESULT v7; // ebx
  int v8; // edi
  unsigned __int64 v9; // rsi
  unsigned __int64 v10; // r12
  unsigned __int16 *v11; // rax
  signed int v12; // ebx
  int ppv; // [rsp+20h] [rbp-E0h]
  void **ppva; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+30h] [rbp-D0h]
  void *v17; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v18[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v19[66]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( a2 || (v6 = 0, a3) )
    v6 = 1;
  if ( !v6 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x14E,
      (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\downloadexecutionbroker.cpp",
      (const char *)0x80070057LL,
      ppv);
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v17 = 0;
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v17);
  v7 = SHCoCreateInstance(0, &CLSID_QueryAssociations, 0, &GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57, &v17);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)v17 + 24LL))(v17, 4, a1);
    if ( v7 >= 0 )
    {
      v8 = 0;
      if ( a2 )
      {
        memset_0(v19, 0, 0x20Au);
        LODWORD(v18[0]) = 261;
        ppva = (void **)v19;
        v8 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)v17 + 32LL))(v17, 0, 2);
        if ( v8 >= 0 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *((_WORD *)v19 + v9) );
          *a2 = 0;
          v10 = v9 + 1;
          if ( v9 + 1 >= v9 && is_mul_ok(v10, 2u) )
          {
            v11 = (unsigned __int16 *)CoTaskMemAlloc(2 * v10);
            *a2 = v11;
            v12 = v11 == 0 ? 0x8007000E : 0;
            if ( v11 )
              StringCchCopyNExW(v11, v9 + 1, (const unsigned __int16 *)v19, v9, v19, v18, v16);
          }
          else
          {
            v12 = -2147024362;
          }
          if ( v12 < 0 )
            wil::details::in1diag3::_FailFast_Hr(
              retaddr,
              (void *)0x16A,
              (int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\downloadexecutionbroker.cpp",
              (const char *)(unsigned int)v12,
              (int)ppva);
        }
      }
      v7 = 0;
      if ( a3 )
        v7 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64))(*(_QWORD *)v17 + 40LL))(v17, 0, 1);
      if ( v7 == v8 || v7 >= 0 && (v8 < 0 || !v7) )
        v7 = v8;
    }
  }
  Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(&v17);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002655c  mov     [rsp-8+arg_18], rbx
0x180026561  push    rbp
0x180026562  push    rsi
0x180026563  push    rdi
0x180026564  push    r12
0x180026566  push    r13
0x180026568  push    r14
0x18002656a  push    r15
0x18002656c  lea     rbp, [rsp-180h]
0x180026574  sub     rsp, 280h
0x18002657b  mov     rax, cs:__security_cookie
0x180026582  xor     rax, rsp
0x180026585  mov     [rbp+1B0h+var_40], rax
0x18002658c  mov     r15, r8
0x18002658f  mov     r14, rdx
0x180026592  mov     rdi, rcx
0x180026595  xor     r13d, r13d
0x180026598  test    rdx, rdx
0x18002659b  jnz     short loc_1800265A5
0x18002659d  test    r8, r8
0x1800265a0  mov     al, r13b
0x1800265a3  jz      short loc_1800265A7
0x1800265a5  mov     al, 1
0x1800265a7  mov     rcx, [rbp+1B8h]; this
0x1800265ae  test    al, al
0x1800265b0  jnz     short loc_1800265CA
0x1800265b2  mov     r9d, 80070057h; char *
0x1800265b8  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x1800265bf  mov     edx, 14Eh; void *
0x1800265c4  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800265ca  test    r14, r14
0x1800265cd  jz      short loc_1800265D2
0x1800265cf  mov     [rdx], r13
0x1800265d2  test    r15, r15
0x1800265d5  jz      short loc_1800265DA
0x1800265d7  mov     [r8], r13
0x1800265da  mov     [rsp+2B0h+var_270], r13
0x1800265df  lea     rcx, [rsp+2B0h+var_270]
0x1800265e4  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x1800265e9  lea     rax, [rsp+2B0h+var_270]
0x1800265ee  mov     [rsp+2B0h+ppv], rax; ppv
0x1800265f3  lea     r9, _GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57; riid
0x1800265fa  xor     r8d, r8d; pUnkOuter
0x1800265fd  lea     rdx, CLSID_QueryAssociations; pclsid
0x180026604  xor     ecx, ecx; pszCLSID
0x180026606  call    cs:__imp_SHCoCreateInstance
0x18002660c  mov     ebx, eax
0x18002660e  test    eax, eax
0x180026610  js      loc_180026761
0x180026616  mov     rcx, [rsp+2B0h+var_270]
0x18002661b  mov     rax, [rcx]
0x18002661e  mov     [rsp+2B0h+ppv], r13
0x180026623  xor     r9d, r9d
0x180026626  mov     r8, rdi
0x180026629  lea     edx, [r9+4]
0x18002662d  mov     rax, [rax+18h]
0x180026631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026636  mov     ebx, eax
0x180026638  test    eax, eax
0x18002663a  js      loc_180026761
0x180026640  mov     edi, r13d
0x180026643  test    r14, r14
0x180026646  jz      loc_180026726
0x18002664c  xor     edx, edx; Val
0x18002664e  mov     r8d, 20Ah; Size
0x180026654  lea     rcx, [rsp+2B0h+var_250]; void *
0x180026659  call    memset_0
0x18002665e  mov     dword ptr [rsp+2B0h+var_268], 105h
0x180026666  mov     rcx, [rsp+2B0h+var_270]
0x18002666b  mov     rax, [rcx]
0x18002666e  lea     rdx, [rsp+2B0h+var_268]
0x180026673  mov     [rsp+2B0h+var_288], rdx; unsigned __int64 *
0x180026678  lea     rdx, [rsp+2B0h+var_250]
0x18002667d  mov     [rsp+2B0h+ppv], rdx; int
0x180026682  xor     r9d, r9d
0x180026685  lea     ebx, [r9+2]
0x180026689  mov     r8d, ebx
0x18002668c  xor     edx, edx
0x18002668e  mov     rax, [rax+20h]
0x180026692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026697  mov     edi, eax
0x180026699  test    eax, eax
0x18002669b  js      loc_180026726
0x1800266a1  lea     rcx, [rsp+2B0h+var_250]
0x1800266a6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800266aa  inc     rsi
0x1800266ad  cmp     [rcx+rsi*2], r13w
0x1800266b2  jnz     short loc_1800266AA
0x1800266b4  mov     [r14], r13
0x1800266b7  lea     r12, [rsi+1]
0x1800266bb  cmp     r12, rsi
0x1800266be  jb      short loc_180026701
0x1800266c0  mov     rax, rbx
0x1800266c3  mul     r12
0x1800266c6  test    rdx, rdx
0x1800266c9  jnz     short loc_180026701
0x1800266cb  mov     rcx, rax; cb
0x1800266ce  call    cs:__imp_CoTaskMemAlloc
0x1800266d4  mov     [r14], rax
0x1800266d7  mov     rcx, rax
0x1800266da  neg     rcx
0x1800266dd  sbb     ebx, ebx
0x1800266df  not     ebx
0x1800266e1  and     ebx, 8007000Eh
0x1800266e7  test    rax, rax
0x1800266ea  jz      short loc_180026706
0x1800266ec  mov     r9, rsi; unsigned __int64
0x1800266ef  lea     r8, [rsp+2B0h+var_250]; unsigned __int16 *
0x1800266f4  mov     rdx, r12; unsigned __int64
0x1800266f7  mov     rcx, rax; unsigned __int16 *
0x1800266fa  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800266ff  jmp     short loc_180026706
0x180026701  mov     ebx, 80070216h
0x180026706  mov     rcx, [rbp+1B8h]; this
0x18002670d  test    ebx, ebx
0x18002670f  jns     short loc_180026726
0x180026711  mov     r9d, ebx; char *
0x180026714  lea     r8, aOnecoreuapInet_6; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18002671b  mov     edx, 16Ah; void *
0x180026720  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180026726  mov     ebx, r13d
0x180026729  test    r15, r15
0x18002672c  jz      short loc_18002674F
0x18002672e  mov     rcx, [rsp+2B0h+var_270]
0x180026733  mov     rax, [rcx]
0x180026736  mov     [rsp+2B0h+ppv], r15
0x18002673b  xor     r9d, r9d
0x18002673e  xor     edx, edx
0x180026740  lea     r8d, [r9+1]
0x180026744  mov     rax, [rax+28h]
0x180026748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002674d  mov     ebx, eax
0x18002674f  cmp     ebx, edi
0x180026751  jz      short loc_18002675F
0x180026753  test    ebx, ebx
0x180026755  js      short loc_180026761
0x180026757  test    edi, edi
0x180026759  js      short loc_18002675F
0x18002675b  test    ebx, ebx
0x18002675d  jnz     short loc_180026761
0x18002675f  mov     ebx, edi
0x180026761  lea     rcx, [rsp+2B0h+var_270]
0x180026766  call    ?InternalRelease@?$ComPtr@UIAssociationElement@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAssociationElement>::InternalRelease(void)
0x18002676b  mov     eax, ebx
0x18002676d  mov     rcx, [rbp+1B0h+var_40]
0x180026774  xor     rcx, rsp; StackCookie
0x180026777  call    __security_check_cookie
0x18002677c  mov     rbx, [rsp+2B0h+arg_18]
0x180026784  add     rsp, 280h
0x18002678b  pop     r15
0x18002678d  pop     r14
0x18002678f  pop     r13
0x180026791  pop     r12
0x180026793  pop     rdi
0x180026794  pop     rsi
0x180026795  pop     rbp
0x180026796  retn
```
