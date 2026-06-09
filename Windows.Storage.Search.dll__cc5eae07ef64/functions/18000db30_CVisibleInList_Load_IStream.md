# CVisibleInList::Load(IStream *)

- ea: `0x18000db30`
- end: `0x18000dd1c`
- name: `?Load@CVisibleInList@@UEAAJPEAUIStream@@@Z`
- size: `492`
- prototype: `int(CVisibleInList *__hidden this, struct IStream *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d660`
- `0x18000dec0`

## callees

- `0x18000db30`
- `0x18000dd24`
- `0x18000dd70`
- `0x18003b150`
- `0x180040b10`
- `0x180071df0`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Read` at `0x18000db6a`
- `SHCORE!IStream_Read` at `0x18000dba6`
- `SHCORE!IStream_Read` at `0x18000db6a`
- `SHCORE!IStream_Read` at `0x18000dba6`
- `SHCORE!IStream_ReadStr` at `0x18000dbec`
- `SHCORE!IStream_ReadStr` at `0x18000dbec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dcad`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18000dc95`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x18000dc95`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000dc65`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18000dc65`

## pseudocode

```c
__int64 __fastcall CVisibleInList::Load(CVisibleInList *this, struct IStream *a2)
{
  HRESULT v4; // ebx
  HDPA v6; // rax
  unsigned int v7; // r14d
  const WCHAR *v8; // rsi
  CVisibleInDescription *v9; // rax
  struct IColumnList *v10; // rdx
  CVisibleInDescription *v11; // rax
  CVisibleInDescription *v12; // rdi
  unsigned int v13; // ebx
  unsigned int pv; // [rsp+60h] [rbp+40h] BYREF
  void *ppv; // [rsp+70h] [rbp+50h] BYREF
  PWSTR ppsz; // [rsp+78h] [rbp+58h] BYREF

  v4 = -2147418113;
  if ( !*((_QWORD *)this + 2) )
  {
    pv = 0;
    v4 = IStream_Read(a2, &pv, 4u);
    if ( v4 >= 0 )
    {
      if ( pv != -2147483647 )
        return (unsigned int)-2147024809;
      pv = 0;
      v4 = IStream_Read(a2, &pv, 4u);
      if ( v4 < 0 )
        return (unsigned int)v4;
      if ( pv )
      {
        v6 = g_pfn_DPA_Create(pv);
        *((_QWORD *)this + 2) = v6;
        v4 = v6 == 0 ? 0x8007000E : 0;
        if ( pv )
        {
          v7 = 0;
          do
          {
            if ( v4 < 0 )
              break;
            ppsz = 0;
            v4 = IStream_ReadStr(a2, &ppsz);
            if ( v4 >= 0 )
            {
              v8 = ppsz;
              ppv = 0;
              v4 = -2147024882;
              v9 = (CVisibleInDescription *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
              if ( v9 )
              {
                v11 = CVisibleInDescription::CVisibleInDescription(v9, v10);
                v12 = v11;
                if ( v11 )
                {
                  if ( !v8 )
                    goto LABEL_23;
                  if ( *((_DWORD *)v11 + 3) == -1 )
                  {
                    v13 = 0;
                    while ( v13 < 0x17 )
                    {
                      if ( !StrCmpICW(v8, (&off_1800ED4A0)[4 * v13]) )
                        *((_DWORD *)v12 + 3) = v13;
                      ++v13;
                      if ( *((_DWORD *)v12 + 3) != -1 )
                      {
                        v4 = 0;
                        goto LABEL_22;
                      }
                    }
                    v4 = -2147024809;
                  }
                  else
                  {
                    v4 = -2147418113;
                  }
LABEL_22:
                  if ( v4 >= 0 )
LABEL_23:
                    v4 = QISearch(v12, &pqit, &GUID_1d17905d_aeb6_4ac9_8cd5_2c103f186212, &ppv);
                  CVisibleInDescription::Release(v12);
                  if ( v4 >= 0 )
                  {
                    if ( DPA_InsertPtr(*((HDPA *)this + 2), 0x7FFFFFFF, ppv) == -1 )
                    {
                      v4 = -2147024882;
                    }
                    else
                    {
                      v4 = 0;
                      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 8LL))(ppv);
                    }
                    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                  }
                }
              }
              CoTaskMemFree(ppsz);
            }
            ++v7;
          }
          while ( v7 < pv );
        }
      }
      else
      {
        return (unsigned int)-2147024809;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000db30  push    rbp
0x18000db32  push    rbx
0x18000db33  push    rsi
0x18000db34  push    rdi
0x18000db35  push    r13
0x18000db37  push    r14
0x18000db39  push    r15
0x18000db3b  mov     rbp, rsp
0x18000db3e  sub     rsp, 20h
0x18000db42  cmp     qword ptr [rcx+10h], 0
0x18000db47  mov     r15, rdx
0x18000db4a  mov     r13, rcx
0x18000db4d  mov     ebx, 8000FFFFh
0x18000db52  jnz     short loc_18000DB84
0x18000db54  mov     edi, 4
0x18000db59  mov     [rbp+pv], 0
0x18000db60  mov     r8d, edi; cb
0x18000db63  lea     rdx, [rbp+pv]; pv
0x18000db67  mov     rcx, r15; pstm
0x18000db6a  call    cs:__imp_IStream_Read
0x18000db70  mov     ebx, eax
0x18000db72  test    eax, eax
0x18000db74  js      short loc_18000DB84
0x18000db76  cmp     [rbp+pv], 80000001h
0x18000db7d  jz      short loc_18000DB95
0x18000db7f  mov     ebx, 80070057h
0x18000db84  mov     eax, ebx
0x18000db86  add     rsp, 20h
0x18000db8a  pop     r15
0x18000db8c  pop     r14
0x18000db8e  pop     r13
0x18000db90  pop     rdi
0x18000db91  pop     rsi
0x18000db92  pop     rbx
0x18000db93  pop     rbp
0x18000db94  retn
0x18000db95  mov     r8d, edi; cb
0x18000db98  mov     [rbp+pv], 0
0x18000db9f  lea     rdx, [rbp+pv]; pv
0x18000dba3  mov     rcx, r15; pstm
0x18000dba6  call    cs:__imp_IStream_Read
0x18000dbac  mov     ebx, eax
0x18000dbae  test    eax, eax
0x18000dbb0  js      short loc_18000DB84
0x18000dbb2  mov     ecx, [rbp+pv]; cItemGrow
0x18000dbb5  test    ecx, ecx
0x18000dbb7  jz      short loc_18000DB7F
0x18000dbb9  call    cs:g_pfn_DPA_Create
0x18000dbbf  mov     [r13+10h], rax
0x18000dbc3  neg     rax
0x18000dbc6  sbb     ebx, ebx
0x18000dbc8  not     ebx
0x18000dbca  and     ebx, 8007000Eh
0x18000dbd0  cmp     [rbp+pv], 0
0x18000dbd4  jbe     short loc_18000DB84
0x18000dbd6  xor     r14d, r14d
0x18000dbd9  test    ebx, ebx
0x18000dbdb  js      short loc_18000DB84
0x18000dbdd  lea     rdx, [rbp+ppsz]; ppsz
0x18000dbe1  mov     [rbp+ppsz], 0
0x18000dbe9  mov     rcx, r15; pstm
0x18000dbec  call    cs:__imp_IStream_ReadStr
0x18000dbf2  mov     ebx, eax
0x18000dbf4  test    eax, eax
0x18000dbf6  js      loc_18000DCB3
0x18000dbfc  mov     rsi, [rbp+ppsz]
0x18000dc00  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000dc07  mov     ecx, 18h; unsigned __int64
0x18000dc0c  mov     [rbp+ppv], 0
0x18000dc14  mov     ebx, 8007000Eh
0x18000dc19  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000dc1e  test    rax, rax
0x18000dc21  jz      loc_18000DCA9
0x18000dc27  mov     rcx, rax; this
0x18000dc2a  call    ??0CVisibleInDescription@@AEAA@PEAUIColumnList@@@Z; CVisibleInDescription::CVisibleInDescription(IColumnList *)
0x18000dc2f  mov     rdi, rax
0x18000dc32  test    rax, rax
0x18000dc35  jz      short loc_18000DCA9
0x18000dc37  test    rsi, rsi
0x18000dc3a  jz      short loc_18000DC80
0x18000dc3c  cmp     dword ptr [rax+0Ch], 0FFFFFFFFh
0x18000dc40  jnz     loc_18000DD12
0x18000dc46  xor     ebx, ebx
0x18000dc48  cmp     ebx, 17h
0x18000dc4b  jnb     loc_18000DD08
0x18000dc51  lea     rax, off_1800ED4A0; "calendar"
0x18000dc58  mov     edx, ebx
0x18000dc5a  shl     rdx, 5
0x18000dc5e  mov     rcx, rsi; pszStr1
0x18000dc61  mov     rdx, [rdx+rax]; pszStr2
0x18000dc65  call    cs:__imp_StrCmpICW
0x18000dc6b  test    eax, eax
0x18000dc6d  jnz     short loc_18000DC72
0x18000dc6f  mov     [rdi+0Ch], ebx
0x18000dc72  inc     ebx
0x18000dc74  cmp     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x18000dc78  jz      short loc_18000DC48
0x18000dc7a  xor     ebx, ebx
0x18000dc7c  test    ebx, ebx
0x18000dc7e  js      short loc_18000DC9D
0x18000dc80  lea     r9, [rbp+ppv]; ppv
0x18000dc84  mov     rcx, rdi; that
0x18000dc87  lea     r8, _GUID_1d17905d_aeb6_4ac9_8cd5_2c103f186212; riid
0x18000dc8e  lea     rdx, pqit; pqit
0x18000dc95  call    cs:__imp_QISearch
0x18000dc9b  mov     ebx, eax
0x18000dc9d  mov     rcx, rdi; this
0x18000dca0  call    ?Release@CVisibleInDescription@@UEAAKXZ; CVisibleInDescription::Release(void)
0x18000dca5  test    ebx, ebx
0x18000dca7  jns     short loc_18000DCC5
0x18000dca9  mov     rcx, [rbp+ppsz]; pv
0x18000dcad  call    cs:__imp_CoTaskMemFree
0x18000dcb3  inc     r14d
0x18000dcb6  cmp     r14d, [rbp+pv]
0x18000dcba  jb      loc_18000DBD9
0x18000dcc0  jmp     loc_18000DB84
0x18000dcc5  mov     r8, [rbp+ppv]; p
0x18000dcc9  mov     edx, 7FFFFFFFh; i
0x18000dcce  mov     rcx, [r13+10h]; hdpa
0x18000dcd2  call    cs:__imp_DPA_InsertPtr
0x18000dcd8  cmp     eax, 0FFFFFFFFh
0x18000dcdb  jz      short loc_18000DD01
0x18000dcdd  mov     rcx, [rbp+ppv]
0x18000dce1  xor     ebx, ebx
0x18000dce3  mov     rax, [rcx]
0x18000dce6  mov     rax, [rax+8]
0x18000dcea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcef  mov     rcx, [rbp+ppv]
0x18000dcf3  mov     rax, [rcx]
0x18000dcf6  mov     rax, [rax+10h]
0x18000dcfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcff  jmp     short loc_18000DCA9
0x18000dd01  mov     ebx, 8007000Eh
0x18000dd06  jmp     short loc_18000DCEF
0x18000dd08  mov     ebx, 80070057h
0x18000dd0d  jmp     loc_18000DC7C
0x18000dd12  mov     ebx, 8000FFFFh
0x18000dd17  jmp     loc_18000DC7C
```
