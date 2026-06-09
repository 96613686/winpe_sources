# CPolicyComponent::Initialize(IWICMetadataQueryReader *)

- ea: `0x180010390`
- end: `0x180010518`
- name: `?Initialize@CPolicyComponent@@UEAAJPEAUIWICMetadataQueryReader@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(CPolicyComponent *__hidden this, struct IWICMetadataQueryReader *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002d50`
- `0x180010390`
- `0x180016020`
- `0x180028010`

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
  try
  {
    v5 = CContainerMasks::EnsureContainerMasksLoaded();
    if ( v5 >= 0 )
    {
      if ( CContainerMasks::m_data )
      {
        v6 = *(_QWORD *)(CContainerMasks::m_data
                       + 8
                       * ((HIDWORD(v17) ^ (unsigned __int64)(DWORD2(v17) ^ DWORD1(v17) ^ (unsigned int)v17))
                        % (unsigned int)dword_180098CB0));
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
  catch ( const ATL::CAtlException *v16 )
  {
    v5 = *(_DWORD *)v16;
    v3 = v15;
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
0x180010390  mov     [rsp+arg_10], rbx
0x180010395  mov     [rsp+arg_18], rsi
0x18001039a  push    rdi
0x18001039b  sub     rsp, 50h
0x18001039f  mov     rax, cs:__security_cookie
0x1800103a6  xor     rax, rsp
0x1800103a9  mov     [rsp+58h+var_10], rax
0x1800103ae  mov     r8, rdx
0x1800103b1  mov     rbx, rcx
0x1800103b4  lea     rsi, [rcx+40h]
0x1800103b8  cmp     byte ptr [rsi], 0
0x1800103bb  jz      short loc_1800103C4
0x1800103bd  xor     eax, eax
0x1800103bf  jmp     loc_1800104FB
0x1800103c4  mov     [rsp+58h+var_30], rsi
0x1800103c9  xorps   xmm0, xmm0
0x1800103cc  movups  [rsp+58h+var_20], xmm0
0x1800103d1  mov     rax, [rdx]
0x1800103d4  lea     rdx, [rsp+58h+var_20]
0x1800103d9  mov     rcx, r8
0x1800103dc  mov     rax, [rax+18h]
0x1800103e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103e5  mov     r9d, eax
0x1800103e8  test    eax, eax
0x1800103ea  js      loc_1800104F4
0x1800103f0  call    ?EnsureContainerMasksLoaded@CContainerMasks@@SAJXZ; CContainerMasks::EnsureContainerMasksLoaded(void)
0x1800103f5  mov     r9d, eax
0x1800103f8  test    eax, eax
0x1800103fa  js      short loc_180010457
0x1800103fc  mov     r10, cs:?m_data@CContainerMasks@@0UStaticData@1@A; CContainerMasks::StaticData CContainerMasks::m_data
0x180010403  test    r10, r10
0x180010406  jz      short loc_180010450
0x180010408  mov     r11, qword ptr [rsp+58h+var_20]
0x18001040d  mov     r8d, r11d
0x180010410  xor     r8d, dword ptr [rsp+58h+var_20+4]
0x180010415  mov     rdi, qword ptr [rsp+58h+var_20+8]
0x18001041a  xor     r8d, edi
0x18001041d  xor     r8d, dword ptr [rsp+58h+var_20+0Ch]
0x180010422  xor     edx, edx
0x180010424  mov     eax, r8d
0x180010427  div     cs:dword_180098CB0
0x18001042d  mov     rax, [r10+rdx*8]
0x180010431  test    rax, rax
0x180010434  jz      short loc_180010450
0x180010436  cmp     [rax+20h], r8d
0x18001043a  jnz     short loc_180010447
0x18001043c  cmp     [rax], r11
0x18001043f  jnz     short loc_180010447
0x180010441  cmp     [rax+8], rdi
0x180010445  jz      short loc_18001045C
0x180010447  mov     rax, [rax+18h]
0x18001044b  test    rax, rax
0x18001044e  jnz     short loc_180010436
0x180010450  mov     dword ptr [rbx+44h], 0
0x180010457  jmp     loc_1800104EB
0x18001045c  mov     ecx, [rax+10h]
0x18001045f  cmp     ecx, 10h
0x180010462  ja      short loc_1800104A3
0x180010464  jz      short loc_18001049A
0x180010466  sub     ecx, 1
0x180010469  jz      short loc_180010491
0x18001046b  sub     ecx, 1
0x18001046e  jz      short loc_180010488
0x180010470  sub     ecx, 2
0x180010473  jz      short loc_18001047F
0x180010475  cmp     ecx, 4
0x180010478  jnz     short loc_180010450
0x18001047a  mov     [rbx+44h], ecx
0x18001047d  jmp     short loc_180010457
0x18001047f  mov     dword ptr [rbx+44h], 3
0x180010486  jmp     short loc_180010457
0x180010488  mov     dword ptr [rbx+44h], 2
0x18001048f  jmp     short loc_180010457
0x180010491  mov     dword ptr [rbx+44h], 1
0x180010498  jmp     short loc_180010457
0x18001049a  mov     dword ptr [rbx+44h], 5
0x1800104a1  jmp     short loc_180010457
0x1800104a3  sub     ecx, 20h ; ' '
0x1800104a6  jz      short loc_1800104D5
0x1800104a8  sub     ecx, 20h ; ' '
0x1800104ab  jz      short loc_1800104CC
0x1800104ad  sub     ecx, 40h ; '@'
0x1800104b0  jz      short loc_1800104C3
0x1800104b2  cmp     ecx, 80h
0x1800104b8  jnz     short loc_180010450
0x1800104ba  mov     dword ptr [rbx+44h], 9
0x1800104c1  jmp     short loc_180010457
0x1800104c3  mov     dword ptr [rbx+44h], 8
0x1800104ca  jmp     short loc_180010457
0x1800104cc  mov     dword ptr [rbx+44h], 7
0x1800104d3  jmp     short loc_180010457
0x1800104d5  mov     dword ptr [rbx+44h], 6
0x1800104dc  jmp     loc_180010457
0x1800104e1  mov     r9d, [rsp+58h+var_38]
0x1800104e6  mov     rsi, [rsp+58h+var_30]
0x1800104eb  test    r9d, r9d
0x1800104ee  js      short loc_1800104F4
0x1800104f0  mov     al, 1
0x1800104f2  jmp     short loc_1800104F6
0x1800104f4  xor     al, al
0x1800104f6  mov     [rsi], al
0x1800104f8  mov     eax, r9d
0x1800104fb  mov     rcx, [rsp+58h+var_10]
0x180010500  xor     rcx, rsp; StackCookie
0x180010503  call    __security_check_cookie
0x180010508  mov     rbx, [rsp+58h+arg_10]
0x18001050d  mov     rsi, [rsp+58h+arg_18]
0x180010512  add     rsp, 50h
0x180010516  pop     rdi
0x180010517  retn
```
