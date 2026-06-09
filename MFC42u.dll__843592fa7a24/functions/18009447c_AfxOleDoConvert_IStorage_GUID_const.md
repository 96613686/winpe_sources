# _AfxOleDoConvert(IStorage *,_GUID const &)

- ea: `0x18009447c`
- end: `0x18009458e`
- name: `?_AfxOleDoConvert@@YAJPEAUIStorage@@AEBU_GUID@@@Z`
- size: `274`
- prototype: `__int64 __fastcall(LPSTORAGE pstg, IID *rclsid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180085f30`

## callees

- `0x18009447c`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009456a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180094560`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009456a`
- `OLE32!SetConvertStg` at `0x180094529`
- `OLE32!SetConvertStg` at `0x180094529`
- `OLE32!WriteFmtUserTypeStg` at `0x180094517`
- `OLE32!WriteFmtUserTypeStg` at `0x18009454d`
- `OLE32!WriteFmtUserTypeStg` at `0x180094517`
- `OLE32!WriteFmtUserTypeStg` at `0x18009454d`
- `OLE32!ReadFmtUserTypeStg` at `0x1800944ce`
- `OLE32!ReadFmtUserTypeStg` at `0x1800944ce`
- `OLE32!OleRegGetUserType` at `0x1800944e8`
- `OLE32!OleRegGetUserType` at `0x1800944e8`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x1800944ad`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x1800944ad`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x180094500`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18009453c`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x180094500`
- `api-ms-win-core-com-l2-1-1!WriteClassStg` at `0x18009453c`

## pseudocode

```c
int __fastcall _AfxOleDoConvert(LPSTORAGE pstg, IID *rclsid)
{
  OLECHAR *v4; // rax
  HRESULT v5; // ebx
  CLIPFORMAT pcf[2]; // [rsp+20h] [rbp-30h] BYREF
  _WORD v8[2]; // [rsp+24h] [rbp-2Ch] BYREF
  LPOLESTR pszUserType; // [rsp+28h] [rbp-28h] BYREF
  LPOLESTR lpszUserType; // [rsp+30h] [rbp-20h] BYREF
  CLSID pclsid; // [rsp+38h] [rbp-18h] BYREF

  pclsid = 0;
  LODWORD(v4) = ReadClassStg(pstg, &pclsid);
  if ( !(_DWORD)v4 )
  {
    pcf[0] = 0;
    lpszUserType = v4;
    ReadFmtUserTypeStg(pstg, pcf, &lpszUserType);
    v8[0] = 0;
    pszUserType = 0;
    if ( OleRegGetUserType(rclsid, 1u, &pszUserType) )
      pszUserType = v8;
    v5 = WriteClassStg(pstg, rclsid);
    if ( !v5 )
    {
      v5 = WriteFmtUserTypeStg(pstg, pcf[0], pszUserType);
      if ( v5 || (v5 = SetConvertStg(pstg, 1)) != 0 )
      {
        WriteClassStg(pstg, &pclsid);
        WriteFmtUserTypeStg(pstg, pcf[0], lpszUserType);
      }
    }
    if ( pszUserType != v8 )
      CoTaskMemFree(pszUserType);
    CoTaskMemFree(lpszUserType);
    LODWORD(v4) = v5;
  }
  return (int)v4;
}

```

## disassembly

```asm
0x18009447c  mov     [rsp-8+arg_10], rbx
0x180094481  mov     [rsp-8+arg_18], rdi
0x180094486  push    rbp
0x180094487  mov     rbp, rsp
0x18009448a  sub     rsp, 50h
0x18009448e  mov     rax, cs:__security_cookie
0x180094495  xor     rax, rsp
0x180094498  mov     [rbp+var_8], rax
0x18009449c  mov     rbx, rdx
0x18009449f  xorps   xmm0, xmm0
0x1800944a2  lea     rdx, [rbp+pclsid]; pclsid
0x1800944a6  mov     rdi, rcx
0x1800944a9  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x1800944ad  call    cs:__imp_ReadClassStg
0x1800944b3  test    eax, eax
0x1800944b5  jnz     loc_180094572
0x1800944bb  lea     r8, [rbp+lpszUserType]; lplpszUserType
0x1800944bf  mov     [rbp+pcf], ax
0x1800944c3  lea     rdx, [rbp+pcf]; pcf
0x1800944c7  mov     [rbp+lpszUserType], rax
0x1800944cb  mov     rcx, rdi; pstg
0x1800944ce  call    cs:__imp_ReadFmtUserTypeStg
0x1800944d4  xor     eax, eax
0x1800944d6  lea     r8, [rbp+pszUserType]; pszUserType
0x1800944da  mov     rcx, rbx; clsid
0x1800944dd  mov     [rbp+var_2C], ax
0x1800944e1  mov     [rbp+pszUserType], rax
0x1800944e5  lea     edx, [rax+1]; dwFormOfType
0x1800944e8  call    cs:__imp_OleRegGetUserType
0x1800944ee  test    eax, eax
0x1800944f0  jz      short loc_1800944FA
0x1800944f2  lea     rax, [rbp+var_2C]
0x1800944f6  mov     [rbp+pszUserType], rax
0x1800944fa  mov     rdx, rbx; rclsid
0x1800944fd  mov     rcx, rdi; pStg
0x180094500  call    cs:__imp_WriteClassStg
0x180094506  mov     ebx, eax
0x180094508  test    eax, eax
0x18009450a  jnz     short loc_180094553
0x18009450c  mov     r8, [rbp+pszUserType]; lpszUserType
0x180094510  mov     rcx, rdi; pstg
0x180094513  movzx   edx, [rbp+pcf]; cf
0x180094517  call    cs:__imp_WriteFmtUserTypeStg
0x18009451d  mov     ebx, eax
0x18009451f  test    eax, eax
0x180094521  jnz     short loc_180094535
0x180094523  lea     edx, [rax+1]; fConvert
0x180094526  mov     rcx, rdi; pStg
0x180094529  call    cs:__imp_SetConvertStg
0x18009452f  mov     ebx, eax
0x180094531  test    eax, eax
0x180094533  jz      short loc_180094553
0x180094535  lea     rdx, [rbp+pclsid]; rclsid
0x180094539  mov     rcx, rdi; pStg
0x18009453c  call    cs:__imp_WriteClassStg
0x180094542  mov     r8, [rbp+lpszUserType]; lpszUserType
0x180094546  mov     rcx, rdi; pstg
0x180094549  movzx   edx, [rbp+pcf]; cf
0x18009454d  call    cs:__imp_WriteFmtUserTypeStg
0x180094553  mov     rcx, [rbp+pszUserType]; pv
0x180094557  lea     rax, [rbp+var_2C]
0x18009455b  cmp     rcx, rax
0x18009455e  jz      short loc_180094566
0x180094560  call    cs:__imp_CoTaskMemFree
0x180094566  mov     rcx, [rbp+lpszUserType]; pv
0x18009456a  call    cs:__imp_CoTaskMemFree
0x180094570  mov     eax, ebx
0x180094572  mov     rcx, [rbp+var_8]
0x180094576  xor     rcx, rsp; StackCookie
0x180094579  call    __security_check_cookie
0x18009457e  mov     rbx, [rsp+50h+arg_10]
0x180094583  mov     rdi, [rsp+50h+arg_18]
0x180094588  add     rsp, 50h
0x18009458c  pop     rbp
0x18009458d  retn
```
