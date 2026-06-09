# CPolicyComponent::Initialize(IWICMetadataQueryReader *)

- ea: `0x180010bb0`
- end: `0x180010d39`
- name: `?Initialize@CPolicyComponent@@UEAAJPEAUIWICMetadataQueryReader@@@Z`
- size: `393`
- prototype: `__int64 __fastcall(CPolicyComponent *__hidden this, struct IWICMetadataQueryReader *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002eb0`
- `0x180010bb0`
- `0x180016a40`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall CPolicyComponent::Initialize(CPolicyComponent *this, struct IWICMetadataQueryReader *a2)
{
  char *v3; // rsi
  int v5; // r9d
  __int64 v6; // rax
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  char v14; // al
  char *v15; // [rsp+28h] [rbp-30h]
  const ATL::CAtlException *v16; // [rsp+30h] [rbp-28h] BYREF
  __int128 v17; // [rsp+38h] [rbp-20h] BYREF

  v3 = (char *)this + 64;
  if ( *((_BYTE *)this + 64) )
    return 0;
  v15 = (char *)this + 64;
  v17 = 0;
  v5 = ((__int64 (__fastcall *)(struct IWICMetadataQueryReader *, __int128 *))a2->lpVtbl->GetContainerFormat)(a2, &v17);
  if ( v5 < 0 )
    goto LABEL_34;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v5 = CContainerMasks::EnsureContainerMasksLoaded();
    if ( v5 >= 0 )
    {
      if ( CContainerMasks::m_data )
      {
        v6 = *(_QWORD *)(CContainerMasks::m_data
                       + 8
                       * ((HIDWORD(v17) ^ (unsigned __int64)(DWORD2(v17) ^ DWORD1(v17) ^ (unsigned int)v17))
                        % (unsigned int)dword_180099DB0));
        if ( v6 )
        {
          while ( *(_DWORD *)(v6 + 32) != (HIDWORD(v17) ^ DWORD2(v17) ^ DWORD1(v17) ^ (unsigned int)v17)
               || *(_OWORD *)v6 != v17 )
          {
            v6 = *(_QWORD *)(v6 + 24);
            if ( !v6 )
              goto LABEL_11;
          }
          v7 = *(_DWORD *)(v6 + 16);
          if ( v7 > 0x10 )
          {
            v11 = v7 - 32;
            if ( !v11 )
            {
              *((_DWORD *)this + 17) = 6;
              goto LABEL_38;
            }
            v12 = v11 - 32;
            if ( !v12 )
            {
              *((_DWORD *)this + 17) = 7;
              goto LABEL_38;
            }
            v13 = v12 - 64;
            if ( !v13 )
            {
              *((_DWORD *)this + 17) = 8;
              goto LABEL_38;
            }
            if ( v13 == 128 )
            {
              *((_DWORD *)this + 17) = 9;
              goto LABEL_38;
            }
          }
          else
          {
            if ( v7 == 16 )
            {
              *((_DWORD *)this + 17) = 5;
              goto LABEL_38;
            }
            v8 = v7 - 1;
            if ( !v8 )
            {
              *((_DWORD *)this + 17) = 1;
              goto LABEL_38;
            }
            v9 = v8 - 1;
            if ( !v9 )
            {
              *((_DWORD *)this + 17) = 2;
              goto LABEL_38;
            }
            v10 = v9 - 2;
            if ( !v10 )
            {
              *((_DWORD *)this + 17) = 3;
              goto LABEL_38;
            }
            if ( v10 == 4 )
            {
              *((_DWORD *)this + 17) = 4;
              goto LABEL_38;
            }
          }
        }
      }
LABEL_11:
      *((_DWORD *)this + 17) = 0;
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v16) )
    {
      v5 = *(_DWORD *)v16;
      v3 = v15;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_180010D01);
    }
  }
LABEL_38:
  if ( v5 < 0 )
  {
LABEL_34:
    v14 = 0;
    goto LABEL_35;
  }
  v14 = 1;
LABEL_35:
  *v3 = v14;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180010bb0  mov     [rsp+arg_10], rbx
0x180010bb5  mov     [rsp+arg_18], rsi
0x180010bba  push    rdi
0x180010bbb  sub     rsp, 50h
0x180010bbf  mov     rax, cs:__security_cookie
0x180010bc6  xor     rax, rsp
0x180010bc9  mov     [rsp+58h+var_10], rax
0x180010bce  mov     r8, rdx
0x180010bd1  mov     rbx, rcx
0x180010bd4  lea     rsi, [rcx+40h]
0x180010bd8  cmp     byte ptr [rsi], 0
0x180010bdb  jz      short loc_180010BE4
0x180010bdd  xor     eax, eax
0x180010bdf  jmp     loc_180010D1B
0x180010be4  mov     [rsp+58h+var_30], rsi
0x180010be9  xorps   xmm0, xmm0
0x180010bec  movups  [rsp+58h+var_20], xmm0
0x180010bf1  mov     rax, [rdx]
0x180010bf4  lea     rdx, [rsp+58h+var_20]
0x180010bf9  mov     rcx, r8
0x180010bfc  mov     rax, [rax+18h]
0x180010c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c05  mov     r9d, eax
0x180010c08  test    eax, eax
0x180010c0a  js      loc_180010D14
0x180010c10  call    ?EnsureContainerMasksLoaded@CContainerMasks@@SAJXZ; CContainerMasks::EnsureContainerMasksLoaded(void)
0x180010c15  mov     r9d, eax
0x180010c18  test    eax, eax
0x180010c1a  js      short loc_180010C77
0x180010c1c  mov     r10, cs:?m_data@CContainerMasks@@0UStaticData@1@A; CContainerMasks::StaticData CContainerMasks::m_data
0x180010c23  test    r10, r10
0x180010c26  jz      short loc_180010C70
0x180010c28  mov     r11, qword ptr [rsp+58h+var_20]
0x180010c2d  mov     r8d, r11d
0x180010c30  xor     r8d, dword ptr [rsp+58h+var_20+4]
0x180010c35  mov     rdi, qword ptr [rsp+58h+var_20+8]
0x180010c3a  xor     r8d, edi
0x180010c3d  xor     r8d, dword ptr [rsp+58h+var_20+0Ch]
0x180010c42  xor     edx, edx
0x180010c44  mov     eax, r8d
0x180010c47  div     cs:dword_180099DB0
0x180010c4d  mov     rax, [r10+rdx*8]
0x180010c51  test    rax, rax
0x180010c54  jz      short loc_180010C70
0x180010c56  cmp     [rax+20h], r8d
0x180010c5a  jnz     short loc_180010C67
0x180010c5c  cmp     [rax], r11
0x180010c5f  jnz     short loc_180010C67
0x180010c61  cmp     [rax+8], rdi
0x180010c65  jz      short loc_180010C7C
0x180010c67  mov     rax, [rax+18h]
0x180010c6b  test    rax, rax
0x180010c6e  jnz     short loc_180010C56
0x180010c70  mov     dword ptr [rbx+44h], 0
0x180010c77  jmp     loc_180010D0B
0x180010c7c  mov     ecx, [rax+10h]
0x180010c7f  cmp     ecx, 10h
0x180010c82  ja      short loc_180010CC3
0x180010c84  jz      short loc_180010CBA
0x180010c86  sub     ecx, 1
0x180010c89  jz      short loc_180010CB1
0x180010c8b  sub     ecx, 1
0x180010c8e  jz      short loc_180010CA8
0x180010c90  sub     ecx, 2
0x180010c93  jz      short loc_180010C9F
0x180010c95  cmp     ecx, 4
0x180010c98  jnz     short loc_180010C70
0x180010c9a  mov     [rbx+44h], ecx
0x180010c9d  jmp     short loc_180010C77
0x180010c9f  mov     dword ptr [rbx+44h], 3
0x180010ca6  jmp     short loc_180010C77
0x180010ca8  mov     dword ptr [rbx+44h], 2
0x180010caf  jmp     short loc_180010C77
0x180010cb1  mov     dword ptr [rbx+44h], 1
0x180010cb8  jmp     short loc_180010C77
0x180010cba  mov     dword ptr [rbx+44h], 5
0x180010cc1  jmp     short loc_180010C77
0x180010cc3  sub     ecx, 20h ; ' '
0x180010cc6  jz      short loc_180010CF5
0x180010cc8  sub     ecx, 20h ; ' '
0x180010ccb  jz      short loc_180010CEC
0x180010ccd  sub     ecx, 40h ; '@'
0x180010cd0  jz      short loc_180010CE3
0x180010cd2  cmp     ecx, 80h
0x180010cd8  jnz     short loc_180010C70
0x180010cda  mov     dword ptr [rbx+44h], 9
0x180010ce1  jmp     short loc_180010C77
0x180010ce3  mov     dword ptr [rbx+44h], 8
0x180010cea  jmp     short loc_180010C77
0x180010cec  mov     dword ptr [rbx+44h], 7
0x180010cf3  jmp     short loc_180010C77
0x180010cf5  mov     dword ptr [rbx+44h], 6
0x180010cfc  jmp     loc_180010C77
0x180010d01  mov     r9d, [rsp+58h+var_38]
0x180010d06  mov     rsi, [rsp+58h+var_30]
0x180010d0b  test    r9d, r9d
0x180010d0e  js      short loc_180010D14
0x180010d10  mov     al, 1
0x180010d12  jmp     short loc_180010D16
0x180010d14  xor     al, al
0x180010d16  mov     [rsi], al
0x180010d18  mov     eax, r9d
0x180010d1b  mov     rcx, [rsp+58h+var_10]
0x180010d20  xor     rcx, rsp; StackCookie
0x180010d23  call    __security_check_cookie
0x180010d28  mov     rbx, [rsp+58h+arg_10]
0x180010d2d  mov     rsi, [rsp+58h+arg_18]
0x180010d32  add     rsp, 50h
0x180010d36  pop     rdi
0x180010d37  retn
```
