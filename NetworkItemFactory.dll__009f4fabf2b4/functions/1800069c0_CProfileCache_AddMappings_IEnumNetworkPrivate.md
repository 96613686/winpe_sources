# CProfileCache::_AddMappings(IEnumNetworkPrivate *)

- ea: `0x1800069c0`
- end: `0x180006bcc`
- name: `?_AddMappings@CProfileCache@@AEAAJPEAUIEnumNetworkPrivate@@@Z`
- size: `524`
- prototype: `__int64 __fastcall(CProfileCache *__hidden this, struct IEnumNetworkPrivate *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006ef4`

## callees

- `0x18000599c`
- `0x1800069c0`
- `0x18000a7d0`
- `0x18000b010`

## import_xrefs

- `ole32!CLSIDFromString` at `0x180006b03`
- `ole32!CLSIDFromString` at `0x180006b03`

## pseudocode

```c
__int64 __fastcall CProfileCache::_AddMappings(CProfileCache *this, struct IEnumNetworkPrivate *a2)
{
  __int64 v2; // rax
  struct IEnumNetworkPrivate *v3; // r15
  HRESULT v5; // eax
  HRESULT v6; // ebx
  unsigned int v7; // r14d
  __int64 v8; // rcx
  unsigned int v9; // edx
  unsigned int v10; // esi
  unsigned int v11; // r8d
  __int64 v12; // r12
  __int64 v13; // r15
  __int64 v14; // r13
  const OLECHAR *v15; // rcx
  __int64 v16; // rax
  unsigned int v18; // [rsp+30h] [rbp-50h] BYREF
  __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  int v20; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 **v21; // [rsp+48h] [rbp-38h] BYREF
  struct IEnumNetworkPrivate *v22; // [rsp+50h] [rbp-30h]
  __int128 v23; // [rsp+58h] [rbp-28h] BYREF
  GUID pclsid; // [rsp+68h] [rbp-18h] BYREF

  v2 = *(_QWORD *)a2;
  v22 = a2;
  v3 = a2;
  v19 = 0;
  v20 = 0;
  v5 = (*(__int64 (__fastcall **)(struct IEnumNetworkPrivate *, __int64, __int64 *, int *))(v2 + 24))(a2, 1, &v19, &v20);
  *((_DWORD *)this + 28) = 0;
  v6 = v5;
  v7 = 0;
  while ( !v6 )
  {
    if ( !*((_DWORD *)this + 28) )
    {
      v18 = 0;
      if ( (*(int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 104LL))(v19, &v18) >= 0 && v18 == 2 )
        *((_DWORD *)this + 28) = 1;
    }
    v23 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 48LL))(v19, &v23);
    if ( v6 >= 0 )
    {
      v8 = *((_QWORD *)this + 1);
      v21 = 0;
      v18 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, unsigned int *, unsigned __int16 ***))(*(_QWORD *)v8 + 80LL))(
             v8,
             &v23,
             &v18,
             &v21);
      if ( v6 >= 0 )
      {
        v9 = v18;
        v10 = 0;
        if ( v18 )
        {
          do
          {
            if ( v6 < 0 )
              break;
            v11 = v7;
            v6 = -2147024809;
            ++v7;
            if ( v11 < *((_DWORD *)this + 4) )
            {
              v12 = v19;
              v13 = 2LL * v11;
              v14 = v11;
              v15 = v21[v10];
              *(_OWORD *)(*((_QWORD *)this + 5) + 16LL * v11) = v23;
              pclsid = 0;
              v6 = CLSIDFromString(v15, &pclsid);
              if ( v6 >= 0 )
              {
                *(GUID *)(*((_QWORD *)this + 4) + 8 * v13) = pclsid;
                v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 24LL))(
                       v12,
                       *((_QWORD *)this + 3) + 8 * v14);
              }
              v9 = v18;
            }
            ++v10;
          }
          while ( v10 < v9 );
          v3 = v22;
        }
        FreeStringArray(v21, v9);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v16 = *(_QWORD *)v3;
        v19 = 0;
        v6 = (*(__int64 (__fastcall **)(struct IEnumNetworkPrivate *, __int64, __int64 *, int *))(v16 + 24))(
               v3,
               1,
               &v19,
               &v20);
      }
    }
  }
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800069c0  mov     [rsp-38h+arg_10], rbx
0x1800069c5  push    rbp
0x1800069c6  push    rsi
0x1800069c7  push    rdi
0x1800069c8  push    r12
0x1800069ca  push    r13
0x1800069cc  push    r14
0x1800069ce  push    r15
0x1800069d0  mov     rbp, rsp
0x1800069d3  sub     rsp, 80h
0x1800069da  mov     rax, cs:__security_cookie
0x1800069e1  xor     rax, rsp
0x1800069e4  mov     [rbp+var_8], rax
0x1800069e8  mov     rax, [rdx]
0x1800069eb  lea     r9, [rbp+var_40]
0x1800069ef  xor     r12d, r12d
0x1800069f2  mov     [rbp+var_30], rdx
0x1800069f6  mov     r15, rdx
0x1800069f9  mov     [rbp+var_48], r12
0x1800069fd  mov     rdi, rcx
0x180006a00  mov     [rbp+var_40], r12d
0x180006a04  mov     rax, [rax+18h]
0x180006a08  lea     r8, [rbp+var_48]
0x180006a0c  lea     edx, [r12+1]
0x180006a11  mov     rcx, r15
0x180006a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a19  mov     [rdi+70h], r12d
0x180006a1d  mov     ebx, eax
0x180006a1f  mov     r14d, r12d
0x180006a22  test    eax, eax
0x180006a24  jnz     loc_180006B8E
0x180006a2a  cmp     [rdi+70h], r12d
0x180006a2e  jnz     short loc_180006A59
0x180006a30  mov     rcx, [rbp+var_48]
0x180006a34  lea     rdx, [rbp+var_50]
0x180006a38  mov     [rbp+var_50], r12d
0x180006a3c  mov     rax, [rcx]
0x180006a3f  mov     rax, [rax+68h]
0x180006a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a48  test    eax, eax
0x180006a4a  js      short loc_180006A59
0x180006a4c  cmp     [rbp+var_50], 2
0x180006a50  jnz     short loc_180006A59
0x180006a52  mov     dword ptr [rdi+70h], 1
0x180006a59  mov     rcx, [rbp+var_48]
0x180006a5d  lea     rdx, [rbp+var_28]
0x180006a61  xorps   xmm0, xmm0
0x180006a64  movups  [rbp+var_28], xmm0
0x180006a68  mov     rax, [rcx]
0x180006a6b  mov     rax, [rax+30h]
0x180006a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a74  mov     ebx, eax
0x180006a76  test    eax, eax
0x180006a78  js      loc_180006B86
0x180006a7e  mov     rcx, [rdi+8]
0x180006a82  lea     r9, [rbp+var_38]
0x180006a86  mov     [rbp+var_38], r12
0x180006a8a  lea     r8, [rbp+var_50]
0x180006a8e  mov     [rbp+var_50], r12d
0x180006a92  lea     rdx, [rbp+var_28]
0x180006a96  mov     rax, [rcx]
0x180006a99  mov     rax, [rax+50h]
0x180006a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aa2  mov     ebx, eax
0x180006aa4  test    eax, eax
0x180006aa6  js      loc_180006B86
0x180006aac  mov     edx, [rbp+var_50]
0x180006aaf  mov     esi, r12d
0x180006ab2  test    edx, edx
0x180006ab4  jz      loc_180006B4B
0x180006aba  test    ebx, ebx
0x180006abc  js      loc_180006B47
0x180006ac2  mov     r8d, r14d
0x180006ac5  mov     ebx, 80070057h
0x180006aca  inc     r14d
0x180006acd  cmp     r8d, [rdi+10h]
0x180006ad1  jnb     short loc_180006B3D
0x180006ad3  mov     rax, [rbp+var_38]
0x180006ad7  lea     rdx, [rbp+pclsid]; pclsid
0x180006adb  movups  xmm0, [rbp+var_28]
0x180006adf  mov     r12, [rbp+var_48]
0x180006ae3  mov     r15d, r8d
0x180006ae6  xorps   xmm1, xmm1
0x180006ae9  mov     ecx, esi
0x180006aeb  add     r15, r15
0x180006aee  mov     r13d, r8d
0x180006af1  mov     rcx, [rax+rcx*8]; lpsz
0x180006af5  mov     rax, [rdi+28h]
0x180006af9  movdqu  xmmword ptr [rax+r15*8], xmm0
0x180006aff  movups  xmmword ptr [rbp+pclsid.Data1], xmm1
0x180006b03  call    cs:__imp_CLSIDFromString
0x180006b09  mov     ebx, eax
0x180006b0b  test    eax, eax
0x180006b0d  js      short loc_180006B37
0x180006b0f  mov     rax, [rdi+20h]
0x180006b13  mov     rcx, r12
0x180006b16  movups  xmm0, xmmword ptr [rbp+pclsid.Data1]
0x180006b1a  movdqu  xmmword ptr [rax+r15*8], xmm0
0x180006b20  mov     rax, [rdi+18h]
0x180006b24  mov     r8, [r12]
0x180006b28  lea     rdx, [rax+r13*8]
0x180006b2c  mov     rax, [r8+18h]
0x180006b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b35  mov     ebx, eax
0x180006b37  mov     edx, [rbp+var_50]; unsigned int
0x180006b3a  xor     r12d, r12d
0x180006b3d  inc     esi
0x180006b3f  cmp     esi, edx
0x180006b41  jb      loc_180006ABA
0x180006b47  mov     r15, [rbp+var_30]
0x180006b4b  mov     rcx, [rbp+var_38]; unsigned __int16 **
0x180006b4f  call    ?FreeStringArray@@YAXPEAPEAGI@Z; FreeStringArray(ushort * *,uint)
0x180006b54  mov     rcx, [rbp+var_48]
0x180006b58  mov     rax, [rcx]
0x180006b5b  mov     rax, [rax+10h]
0x180006b5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b64  mov     rax, [r15]
0x180006b67  lea     r9, [rbp+var_40]
0x180006b6b  lea     r8, [rbp+var_48]
0x180006b6f  mov     [rbp+var_48], r12
0x180006b73  mov     edx, 1
0x180006b78  mov     rcx, r15
0x180006b7b  mov     rax, [rax+18h]
0x180006b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b84  mov     ebx, eax
0x180006b86  test    ebx, ebx
0x180006b88  jz      loc_180006A2A
0x180006b8e  mov     rcx, [rbp+var_48]
0x180006b92  test    rcx, rcx
0x180006b95  jz      short loc_180006BA3
0x180006b97  mov     rax, [rcx]
0x180006b9a  mov     rax, [rax+10h]
0x180006b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba3  mov     eax, ebx
0x180006ba5  mov     rcx, [rbp+var_8]
0x180006ba9  xor     rcx, rsp; StackCookie
0x180006bac  call    __security_check_cookie
0x180006bb1  mov     rbx, [rsp+80h+arg_10]
0x180006bb9  add     rsp, 80h
0x180006bc0  pop     r15
0x180006bc2  pop     r14
0x180006bc4  pop     r13
0x180006bc6  pop     r12
0x180006bc8  pop     rdi
0x180006bc9  pop     rsi
0x180006bca  pop     rbp
0x180006bcb  retn
```
