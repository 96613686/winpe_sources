# CCachedFolderItem::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x18004e1d0`
- end: `0x18004e357`
- name: `?GetValue@CCachedFolderItem@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(CCachedFolderItem *this, const struct _tagpropertykey *, PROPVARIANT *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180033dd0`
- `0x18004e1d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e344`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004e344`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e2bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e2d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e325`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e2bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e2d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004e325`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004e2e2`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18004e2e2`
- `PROPSYS!InitPropVariantFromFileTime` at `0x18004e2b1`
- `PROPSYS!InitPropVariantFromFileTime` at `0x18004e2b1`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18004e299`
- `PROPSYS!InitPropVariantFromCLSID` at `0x18004e299`

## pseudocode

```c
__int64 __fastcall CCachedFolderItem::GetValue(
        CCachedFolderItem *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3)
{
  unsigned int v5; // r8d
  unsigned int v6; // ebp
  __int64 v7; // r14
  __int64 v8; // rax
  __int16 v9; // ax
  const unsigned __int16 *v11; // rcx
  HRESULT inited; // eax
  LONG v13; // ecx
  bool v14; // cf

  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  v5 = 0;
  v6 = -2147024809;
  while ( 1 )
  {
    if ( v5 >= 0x10 )
      return v6;
    v7 = (int)v5;
    if ( a2->pid == LODWORD(qword_1800702C0[3 * (int)v5 + 2]) )
    {
      v8 = *(_QWORD *)&a2->fmtid.Data1 - qword_1800702C0[3 * (int)v5];
      if ( *(_QWORD *)&a2->fmtid.Data1 == qword_1800702C0[3 * (int)v5] )
        v8 = *(_QWORD *)a2->fmtid.Data4 - qword_1800702C0[3 * (int)v5 + 1];
      if ( !v8 )
        break;
    }
    ++v5;
  }
  v6 = 1;
  if ( *((_DWORD *)this + 366) || !BYTE6(qword_1800702C0[3 * (int)v5 + 2]) )
  {
    v9 = WORD2(qword_1800702C0[3 * (int)v5 + 2]);
    if ( v9 != 8 )
    {
      if ( v9 == 11 )
      {
        _mm_lfence();
        v14 = **((_DWORD **)this + (int)v5 + 185) != 0;
        *(_WORD *)a3 = 11;
        *((_WORD *)a3 + 4) = -v14;
      }
      else
      {
        if ( v9 != 23 )
        {
          if ( v9 == 29 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
            inited = PropVariantCopy(a3, *((const PROPVARIANT **)this + v7 + 185));
LABEL_27:
            v6 = inited;
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
            return v6;
          }
          if ( v9 != 31 )
          {
            if ( v9 == 64 )
            {
              return (unsigned int)InitPropVariantFromFileTime(*((const FILETIME **)this + (int)v5 + 185), a3);
            }
            else
            {
              if ( v9 != 72 )
                return v6;
              return (unsigned int)InitPropVariantFromCLSID(*((const IID *const *)this + (int)v5 + 185), a3);
            }
          }
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
          v11 = (const unsigned __int16 *)*((_QWORD *)this + v7 + 185);
LABEL_26:
          inited = InitPropVariantFromString(v11, (struct tagPROPVARIANT *)a3);
          goto LABEL_27;
        }
        _mm_lfence();
        v13 = **((_DWORD **)this + (int)v5 + 185);
        *(_WORD *)a3 = 19;
        *((_DWORD *)a3 + 2) = v13;
      }
      return 0;
    }
    _mm_lfence();
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    v11 = (const unsigned __int16 *)**((_QWORD **)this + v7 + 185);
    goto LABEL_26;
  }
  return v6;
}

```

## disassembly

```asm
0x18004e1d0  push    rbx
0x18004e1d2  push    rbp
0x18004e1d3  push    rsi
0x18004e1d4  push    rdi
0x18004e1d5  push    r14
0x18004e1d7  sub     rsp, 20h
0x18004e1db  xor     eax, eax
0x18004e1dd  lea     r9, qword_1800702C0
0x18004e1e4  xorps   xmm0, xmm0
0x18004e1e7  mov     rsi, r8
0x18004e1ea  movups  xmmword ptr [r8], xmm0
0x18004e1ee  mov     [r8+10h], rax
0x18004e1f2  mov     rdi, rcx
0x18004e1f5  xor     r8d, r8d
0x18004e1f8  mov     ebp, 80070057h
0x18004e1fd  cmp     r8d, 10h
0x18004e201  jnb     loc_18004E34A
0x18004e207  movsxd  r14, r8d
0x18004e20a  lea     rcx, [r14+r14*2]
0x18004e20e  mov     eax, [r9+rcx*8+10h]
0x18004e213  cmp     [rdx+10h], eax
0x18004e216  jnz     short loc_18004E22F
0x18004e218  mov     rax, [rdx]
0x18004e21b  sub     rax, [r9+rcx*8]
0x18004e21f  jnz     short loc_18004E22A
0x18004e221  mov     rax, [rdx+8]
0x18004e225  sub     rax, [r9+rcx*8+8]
0x18004e22a  test    rax, rax
0x18004e22d  jz      short loc_18004E234
0x18004e22f  inc     r8d
0x18004e232  jmp     short loc_18004E1FD
0x18004e234  cmp     dword ptr [rdi+5B8h], 0
0x18004e23b  mov     ebp, 1
0x18004e240  jnz     short loc_18004E24E
0x18004e242  cmp     byte ptr [r9+rcx*8+16h], 0
0x18004e248  jnz     loc_18004E34A
0x18004e24e  movzx   eax, word ptr [r9+rcx*8+14h]
0x18004e254  cmp     ax, 8
0x18004e258  jz      loc_18004E31E
0x18004e25e  mov     edx, 0Bh
0x18004e263  cmp     ax, dx
0x18004e266  jz      loc_18004E303
0x18004e26c  cmp     ax, 17h
0x18004e270  jz      short loc_18004E2EA
0x18004e272  cmp     ax, 1Dh
0x18004e276  jz      short loc_18004E2CD
0x18004e278  cmp     ax, 1Fh
0x18004e27c  jz      short loc_18004E2B9
0x18004e27e  cmp     ax, 40h ; '@'
0x18004e282  jz      short loc_18004E2A6
0x18004e284  cmp     ax, 48h ; 'H'
0x18004e288  jnz     loc_18004E34A
0x18004e28e  mov     rcx, [rdi+r14*8+5C8h]; clsid
0x18004e296  mov     rdx, rsi; ppropvar
0x18004e299  call    cs:__imp_InitPropVariantFromCLSID
0x18004e29f  mov     ebp, eax
0x18004e2a1  jmp     loc_18004E34A
0x18004e2a6  mov     rcx, [rdi+r14*8+5C8h]; pftIn
0x18004e2ae  mov     rdx, rsi; ppropvar
0x18004e2b1  call    cs:__imp_InitPropVariantFromFileTime
0x18004e2b7  jmp     short loc_18004E29F
0x18004e2b9  lea     rcx, [rdi+18h]; lpCriticalSection
0x18004e2bd  call    cs:__imp_EnterCriticalSection
0x18004e2c3  mov     rcx, [rdi+r14*8+5C8h]
0x18004e2cb  jmp     short loc_18004E336
0x18004e2cd  lea     rcx, [rdi+18h]; lpCriticalSection
0x18004e2d1  call    cs:__imp_EnterCriticalSection
0x18004e2d7  mov     rdx, [rdi+r14*8+5C8h]; pvarSrc
0x18004e2df  mov     rcx, rsi; pvarDest
0x18004e2e2  call    cs:__imp_PropVariantCopy
0x18004e2e8  jmp     short loc_18004E33E
0x18004e2ea  lfence
0x18004e2ed  mov     rax, [rdi+r14*8+5C8h]
0x18004e2f5  mov     ecx, [rax]
0x18004e2f7  mov     word ptr [rsi], 13h
0x18004e2fc  mov     [rsi+8], ecx
0x18004e2ff  xor     ebp, ebp
0x18004e301  jmp     short loc_18004E34A
0x18004e303  lfence
0x18004e306  mov     rax, [rdi+r14*8+5C8h]
0x18004e30e  mov     ecx, [rax]
0x18004e310  neg     ecx
0x18004e312  mov     [rsi], dx
0x18004e315  sbb     ax, ax
0x18004e318  mov     [rsi+8], ax
0x18004e31c  jmp     short loc_18004E2FF
0x18004e31e  lfence
0x18004e321  lea     rcx, [rdi+18h]; lpCriticalSection
0x18004e325  call    cs:__imp_EnterCriticalSection
0x18004e32b  mov     rcx, [rdi+r14*8+5C8h]
0x18004e333  mov     rcx, [rcx]; Source
0x18004e336  mov     rdx, rsi; struct tagPROPVARIANT *
0x18004e339  call    ?InitPropVariantFromString@@YAJPEBGPEAUtagPROPVARIANT@@@Z; InitPropVariantFromString(ushort const *,tagPROPVARIANT *)
0x18004e33e  lea     rcx, [rdi+18h]; lpCriticalSection
0x18004e342  mov     ebp, eax
0x18004e344  call    cs:__imp_LeaveCriticalSection
0x18004e34a  mov     eax, ebp
0x18004e34c  add     rsp, 20h
0x18004e350  pop     r14
0x18004e352  pop     rdi
0x18004e353  pop     rsi
0x18004e354  pop     rbp
0x18004e355  pop     rbx
0x18004e356  retn
```
