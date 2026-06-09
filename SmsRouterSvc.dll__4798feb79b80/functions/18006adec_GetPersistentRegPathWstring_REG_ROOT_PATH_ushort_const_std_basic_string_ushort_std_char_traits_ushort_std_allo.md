# GetPersistentRegPathWstring(_REG_ROOT_PATH,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18006adec`
- end: `0x18006afad`
- name: `?GetPersistentRegPathWstring@@YAKW4_REG_ROOT_PATH@@PEBGPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18006afb4`

## callees

- `0x180003a60`
- `0x1800069f0`
- `0x180051980`
- `0x18006989c`
- `0x18006adec`

## import_xrefs

- `MobileNetworking!GetPersistentRegPath` at `0x18006aec0`
- `MobileNetworking!GetPersistentRegPath` at `0x18006aec0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetPersistentRegPathWstring(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // rdi
  unsigned int v6; // esi
  unsigned int v7; // eax
  __int128 *v8; // rcx
  __int128 *p_Src; // r9
  _WORD *v10; // rdi
  unsigned __int64 i; // rcx
  __int128 *v12; // r9
  unsigned int PersistentRegPath; // eax
  unsigned int v14; // ebx
  unsigned int v15; // ecx
  unsigned __int64 v16; // r8
  unsigned __int64 v17; // rcx
  __int128 *v18; // rcx
  unsigned __int64 v19; // rdx
  __int128 *v20; // r9
  _WORD *v21; // rdi
  unsigned __int64 j; // rcx
  int v24; // [rsp+30h] [rbp-58h] BYREF
  __int128 Src; // [rsp+38h] [rbp-50h] BYREF
  unsigned __int64 v26; // [rsp+48h] [rbp-40h]
  unsigned __int64 v27; // [rsp+50h] [rbp-38h]

  Src = 0;
  v4 = 0;
  v26 = 0;
  v5 = 7;
  v27 = 7;
  LOWORD(Src) = 0;
  v6 = 0;
  v7 = 512;
  v24 = 512;
  try
  {
    while ( 1 )
    {
      if ( v7 > v4 )
      {
        if ( v7 - v4 > v5 - v4 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(&Src);
        }
        else
        {
          v26 = v7;
          p_Src = &Src;
          if ( v5 > 7 )
            p_Src = (__int128 *)Src;
          v10 = (_WORD *)p_Src + v4;
          if ( v7 != v4 )
          {
            for ( i = v7 - v4; i; --i )
              *v10++ = 0;
          }
          *((_WORD *)p_Src + v7) = 0;
        }
      }
      else
      {
        v26 = v7;
        v8 = &Src;
        if ( v5 > 7 )
          v8 = (__int128 *)Src;
        *((_WORD *)v8 + v7) = 0;
      }
      v12 = &Src;
      if ( v27 > 7 )
        v12 = (__int128 *)Src;
      PersistentRegPath = GetPersistentRegPath(1, 0, &v24, v12);
      v14 = PersistentRegPath;
      if ( PersistentRegPath != 234 )
        break;
      v15 = v6++;
      if ( v15 >= 3 )
        break;
      v5 = v27;
      v4 = v26;
      v7 = v24;
    }
    if ( !PersistentRegPath )
    {
      v16 = (unsigned int)(v24 - 1);
      v17 = v26;
      if ( v16 > v26 )
      {
        v19 = v16 - v26;
        if ( v16 - v26 > v27 - v26 )
        {
          ____Reallocate_grow_by_V_lambda_1___1__append___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAAEAV34__KG_Z__KG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__append_01_QEAAAEAV01_0G_Z__KG_Z(&Src);
        }
        else
        {
          v26 = (unsigned int)(v24 - 1);
          v20 = &Src;
          if ( v27 > 7 )
            v20 = (__int128 *)Src;
          v21 = (_WORD *)v20 + v17;
          if ( v19 )
          {
            for ( j = v16 - v17; j; --j )
              *v21++ = 0;
          }
          *((_WORD *)v20 + v16) = 0;
        }
      }
      else
      {
        v26 = (unsigned int)(v24 - 1);
        v18 = &Src;
        if ( v27 > 7 )
          v18 = (__int128 *)Src;
        *((_WORD *)v18 + v16) = 0;
      }
      std::wstring::operator=(a3, &Src);
    }
    std::wstring::~wstring((char **)&Src);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( ... )
  {
    return 31;
  }
  return v14;
}

```

## disassembly

```asm
0x18006adec  push    rbx
0x18006adee  push    rsi
0x18006adef  push    rdi
0x18006adf0  push    r14
0x18006adf2  sub     rsp, 68h
0x18006adf6  mov     rax, cs:__security_cookie
0x18006adfd  xor     rax, rsp
0x18006ae00  mov     [rsp+88h+var_30], rax
0x18006ae05  mov     r14, r8
0x18006ae08  xorps   xmm0, xmm0
0x18006ae0b  movups  [rsp+88h+Src], xmm0
0x18006ae10  xor     ecx, ecx
0x18006ae12  mov     [rsp+88h+var_40], rcx
0x18006ae17  lea     edi, [rcx+7]
0x18006ae1a  mov     [rsp+88h+var_38], rdi
0x18006ae1f  xor     eax, eax
0x18006ae21  mov     word ptr [rsp+88h+Src], ax
0x18006ae26  xor     esi, esi
0x18006ae28  mov     eax, 200h
0x18006ae2d  mov     [rsp+88h+var_58], eax
0x18006ae31  mov     r8d, eax
0x18006ae34  cmp     r8, rcx
0x18006ae37  ja      short loc_18006AE56
0x18006ae39  mov     [rsp+88h+var_40], r8
0x18006ae3e  lea     rcx, [rsp+88h+Src]
0x18006ae43  cmp     rdi, 7
0x18006ae47  cmova   rcx, qword ptr [rsp+88h+Src]
0x18006ae4d  xor     eax, eax
0x18006ae4f  mov     [rcx+r8*2], ax
0x18006ae54  jmp     short loc_18006AEA5
0x18006ae56  mov     rdx, r8
0x18006ae59  sub     rdx, rcx
0x18006ae5c  mov     rax, rdi
0x18006ae5f  sub     rax, rcx
0x18006ae62  cmp     rdx, rax
0x18006ae65  ja      short loc_18006AE98
0x18006ae67  mov     [rsp+88h+var_40], r8
0x18006ae6c  lea     r9, [rsp+88h+Src]
0x18006ae71  cmp     rdi, 7
0x18006ae75  cmova   r9, qword ptr [rsp+88h+Src]
0x18006ae7b  lea     rdi, [r9+rcx*2]
0x18006ae7f  test    rdx, rdx
0x18006ae82  jz      short loc_18006AE8F
0x18006ae84  xor     eax, eax
0x18006ae86  movzx   eax, ax
0x18006ae89  mov     rcx, rdx
0x18006ae8c  rep stosw
0x18006ae8f  xor     eax, eax
0x18006ae91  mov     [r9+r8*2], ax
0x18006ae96  jmp     short loc_18006AEA5
0x18006ae98  mov     r9, rdx
0x18006ae9b  lea     rcx, [rsp+88h+Src]; Src
0x18006aea0  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18006aea5  lea     r9, [rsp+88h+Src]
0x18006aeaa  cmp     [rsp+88h+var_38], 7
0x18006aeb0  cmova   r9, qword ptr [rsp+88h+Src]
0x18006aeb6  lea     r8, [rsp+88h+var_58]
0x18006aebb  xor     edx, edx
0x18006aebd  lea     ecx, [rdx+1]
0x18006aec0  call    cs:__imp_GetPersistentRegPath
0x18006aec6  mov     ebx, eax
0x18006aec8  cmp     eax, 0EAh
0x18006aecd  jnz     short loc_18006AEEB
0x18006aecf  mov     ecx, esi
0x18006aed1  inc     esi
0x18006aed3  cmp     ecx, 3
0x18006aed6  jnb     short loc_18006AEEB
0x18006aed8  mov     rdi, [rsp+88h+var_38]
0x18006aedd  mov     rcx, [rsp+88h+var_40]
0x18006aee2  mov     eax, [rsp+88h+var_58]
0x18006aee6  jmp     loc_18006AE31
0x18006aeeb  test    eax, eax
0x18006aeed  jnz     loc_18006AF83
0x18006aef3  mov     r8d, [rsp+88h+var_58]
0x18006aef8  dec     r8d
0x18006aefb  mov     rcx, [rsp+88h+var_40]
0x18006af00  cmp     r8, rcx
0x18006af03  ja      short loc_18006AF22
0x18006af05  mov     [rsp+88h+var_40], r8
0x18006af0a  lea     rcx, [rsp+88h+Src]
0x18006af0f  cmp     [rsp+88h+var_38], 7
0x18006af15  cmova   rcx, qword ptr [rsp+88h+Src]
0x18006af1b  mov     [rcx+r8*2], ax
0x18006af20  jmp     short loc_18006AF75
0x18006af22  mov     rdx, r8
0x18006af25  sub     rdx, rcx
0x18006af28  mov     rax, [rsp+88h+var_38]
0x18006af2d  sub     rax, rcx
0x18006af30  cmp     rdx, rax
0x18006af33  ja      short loc_18006AF68
0x18006af35  mov     [rsp+88h+var_40], r8
0x18006af3a  lea     r9, [rsp+88h+Src]
0x18006af3f  cmp     [rsp+88h+var_38], 7
0x18006af45  cmova   r9, qword ptr [rsp+88h+Src]
0x18006af4b  lea     rdi, [r9+rcx*2]
0x18006af4f  test    rdx, rdx
0x18006af52  jz      short loc_18006AF5F
0x18006af54  xor     eax, eax
0x18006af56  movzx   eax, ax
0x18006af59  mov     rcx, rdx
0x18006af5c  rep stosw
0x18006af5f  xor     eax, eax
0x18006af61  mov     [r9+r8*2], ax
0x18006af66  jmp     short loc_18006AF75
0x18006af68  mov     r9, rdx
0x18006af6b  lea     rcx, [rsp+88h+Src]; Src
0x18006af70  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV34@_KG@Z@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??append@01@QEAAAEAV01@0G@Z@_KG@Z; std::wstring::_Reallocate_grow_by<`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort>(unsigned __int64,`std::wstring::append(unsigned __int64,ushort)'::`2'::_lambda_1_,unsigned __int64,ushort)
0x18006af75  lea     rdx, [rsp+88h+Src]
0x18006af7a  mov     rcx, r14
0x18006af7d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006af82  nop
0x18006af83  lea     rcx, [rsp+88h+Src]; void *
0x18006af88  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006af8d  nop
0x18006af8e  jmp     short loc_18006AF94
0x18006af90  mov     ebx, [rsp+88h+var_58]
0x18006af94  mov     eax, ebx
0x18006af96  mov     rcx, [rsp+88h+var_30]
0x18006af9b  xor     rcx, rsp; StackCookie
0x18006af9e  call    __security_check_cookie
0x18006afa3  add     rsp, 68h
0x18006afa7  pop     r14
0x18006afa9  pop     rdi
0x18006afaa  pop     rsi
0x18006afab  pop     rbx
0x18006afac  retn
```
