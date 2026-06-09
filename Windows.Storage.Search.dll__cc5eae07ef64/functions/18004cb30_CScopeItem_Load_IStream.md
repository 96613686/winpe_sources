# CScopeItem::Load(IStream *)

- ea: `0x18004cb30`
- end: `0x18004ccdc`
- name: `?Load@CScopeItem@@UEAAJPEAUIStream@@@Z`
- size: `428`
- prototype: `int(CScopeItem *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18004cb30`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Read` at `0x18004cb58`
- `SHCORE!IStream_Read` at `0x18004cb75`
- `SHCORE!IStream_Read` at `0x18004cb92`
- `SHCORE!IStream_Read` at `0x18004cbb8`
- `SHCORE!IStream_Read` at `0x18004ccbb`
- `SHCORE!IStream_Read` at `0x18004cb58`
- `SHCORE!IStream_Read` at `0x18004cb75`
- `SHCORE!IStream_Read` at `0x18004cb92`
- `SHCORE!IStream_Read` at `0x18004cbb8`
- `SHCORE!IStream_Read` at `0x18004ccbb`
- `SHCORE!IStream_ReadStr` at `0x18004cc9c`
- `SHCORE!IStream_ReadStr` at `0x18004cc9c`
- `Windows.Storage!ILFree` at `0x18004cc03`
- `Windows.Storage!ILFree` at `0x18004cc6e`
- `Windows.Storage!ILFree` at `0x18004cc03`
- `Windows.Storage!ILFree` at `0x18004cc6e`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18004cc4c`
- `Windows.Storage!SHCreateItemFromIDList` at `0x18004cc4c`
- `Windows.Storage!ILClone` at `0x18004cc15`
- `Windows.Storage!ILClone` at `0x18004cc15`
- `Windows.Storage!__imp_ILLoadFromStreamEx` at `0x18004cbee`
- `Windows.Storage!__imp_ILLoadFromStreamEx` at `0x18004cbee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004cb45`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004cb45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004cc78`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004cc78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cc8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004cc8f`

## pseudocode

```c
__int64 __fastcall CScopeItem::Load(CScopeItem *this, struct IStream *a2)
{
  HRESULT Str; // ebx
  const ITEMIDLIST *v5; // rbx
  const ITEMIDLIST *v6; // rax
  int pv; // [rsp+50h] [rbp+8h] BYREF
  LPITEMIDLIST pidl; // [rsp+60h] [rbp+18h] BYREF
  void *ppv; // [rsp+68h] [rbp+20h] BYREF

  AcquireSRWLockExclusive((PSRWLOCK)this + 7);
  Str = IStream_Read(a2, (char *)this + 20, 4u);
  if ( Str >= 0 )
  {
    Str = IStream_Read(a2, (char *)this + 16, 4u);
    if ( Str >= 0 )
    {
      Str = IStream_Read(a2, (char *)this + 24, 4u);
      if ( Str >= 0 )
      {
        pv = 0;
        Str = IStream_Read(a2, &pv, 4u);
        if ( Str >= 0 )
        {
          if ( !pv || (CoTaskMemFree(*((LPVOID *)this + 6)), Str = IStream_ReadStr(a2, (PWSTR *)this + 6), Str >= 0) )
          {
            if ( (*((_BYTE *)this + 24) & 2) == 0 || (Str = IStream_Read(a2, (char *)this + 28, 0x10u), Str >= 0) )
            {
              pidl = 0;
              Str = ILLoadFromStreamEx(a2, &pidl);
              if ( Str >= 0 )
              {
                v5 = pidl;
                ILFree(*((LPITEMIDLIST *)this + 1));
                if ( v5 )
                {
                  v6 = ILClone(v5);
                  *((_QWORD *)this + 1) = v6;
                  Str = v6 == 0 ? 0x8007000E : 0;
                  if ( v6 )
                  {
                    ppv = 0;
                    Str = SHCreateItemFromIDList(v6, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
                    if ( Str >= 0 )
                      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                  }
                }
                else
                {
                  Str = -2147024809;
                  *((_QWORD *)this + 1) = 0;
                }
                ILFree(pidl);
              }
            }
          }
        }
      }
    }
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this + 7);
  return (unsigned int)Str;
}

```

## disassembly

```asm
0x18004cb30  push    rbx
0x18004cb32  push    rbp
0x18004cb33  push    rsi
0x18004cb34  push    rdi
0x18004cb35  push    r14
0x18004cb37  sub     rsp, 20h
0x18004cb3b  mov     rdi, rcx
0x18004cb3e  mov     rsi, rdx
0x18004cb41  add     rcx, 38h ; '8'; SRWLock
0x18004cb45  call    cs:__imp_AcquireSRWLockExclusive
0x18004cb4b  lea     rdx, [rdi+14h]; pv
0x18004cb4f  mov     r8d, 4; cb
0x18004cb55  mov     rcx, rsi; pstm
0x18004cb58  call    cs:__imp_IStream_Read
0x18004cb5e  mov     ebx, eax
0x18004cb60  test    eax, eax
0x18004cb62  js      loc_18004CC74
0x18004cb68  lea     rdx, [rdi+10h]; pv
0x18004cb6c  mov     r8d, 4; cb
0x18004cb72  mov     rcx, rsi; pstm
0x18004cb75  call    cs:__imp_IStream_Read
0x18004cb7b  mov     ebx, eax
0x18004cb7d  test    eax, eax
0x18004cb7f  js      loc_18004CC74
0x18004cb85  mov     r8d, 4; cb
0x18004cb8b  lea     rdx, [rdi+18h]; pv
0x18004cb8f  mov     rcx, rsi; pstm
0x18004cb92  call    cs:__imp_IStream_Read
0x18004cb98  mov     ebx, eax
0x18004cb9a  test    eax, eax
0x18004cb9c  js      loc_18004CC74
0x18004cba2  mov     r8d, 4; cb
0x18004cba8  mov     [rsp+48h+pv], 0
0x18004cbb0  lea     rdx, [rsp+48h+pv]; pv
0x18004cbb5  mov     rcx, rsi; pstm
0x18004cbb8  call    cs:__imp_IStream_Read
0x18004cbbe  mov     ebx, eax
0x18004cbc0  test    eax, eax
0x18004cbc2  js      loc_18004CC74
0x18004cbc8  cmp     [rsp+48h+pv], 0
0x18004cbcd  jnz     loc_18004CC8B
0x18004cbd3  test    byte ptr [rdi+18h], 2
0x18004cbd7  jnz     loc_18004CCAE
0x18004cbdd  lea     rdx, [rsp+48h+pidl]; pidl
0x18004cbe2  mov     [rsp+48h+pidl], 0
0x18004cbeb  mov     rcx, rsi; pstm
0x18004cbee  call    cs:__imp_ILLoadFromStreamEx
0x18004cbf4  mov     ebx, eax
0x18004cbf6  test    eax, eax
0x18004cbf8  js      short loc_18004CC74
0x18004cbfa  mov     rcx, [rdi+8]; pidl
0x18004cbfe  mov     rbx, [rsp+48h+pidl]
0x18004cc03  call    cs:__imp_ILFree
0x18004cc09  test    rbx, rbx
0x18004cc0c  jz      loc_18004CCCD
0x18004cc12  mov     rcx, rbx; pidl
0x18004cc15  call    cs:__imp_ILClone
0x18004cc1b  mov     rcx, rax
0x18004cc1e  mov     [rdi+8], rax
0x18004cc22  neg     rcx
0x18004cc25  sbb     ebx, ebx
0x18004cc27  not     ebx
0x18004cc29  and     ebx, 8007000Eh
0x18004cc2f  test    rax, rax
0x18004cc32  jz      short loc_18004CC69
0x18004cc34  lea     r8, [rsp+48h+ppv]; ppv
0x18004cc39  mov     [rsp+48h+ppv], 0
0x18004cc42  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18004cc49  mov     rcx, rax; pidl
0x18004cc4c  call    cs:__imp_SHCreateItemFromIDList
0x18004cc52  mov     ebx, eax
0x18004cc54  test    eax, eax
0x18004cc56  js      short loc_18004CC69
0x18004cc58  mov     rcx, [rsp+48h+ppv]
0x18004cc5d  mov     rax, [rcx]
0x18004cc60  mov     rax, [rax+10h]
0x18004cc64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc69  mov     rcx, [rsp+48h+pidl]; pidl
0x18004cc6e  call    cs:__imp_ILFree
0x18004cc74  lea     rcx, [rdi+38h]; SRWLock
0x18004cc78  call    cs:__imp_ReleaseSRWLockExclusive
0x18004cc7e  mov     eax, ebx
0x18004cc80  add     rsp, 20h
0x18004cc84  pop     r14
0x18004cc86  pop     rdi
0x18004cc87  pop     rsi
0x18004cc88  pop     rbp
0x18004cc89  pop     rbx
0x18004cc8a  retn
0x18004cc8b  mov     rcx, [rdi+30h]; pv
0x18004cc8f  call    cs:__imp_CoTaskMemFree
0x18004cc95  lea     rdx, [rdi+30h]; ppsz
0x18004cc99  mov     rcx, rsi; pstm
0x18004cc9c  call    cs:__imp_IStream_ReadStr
0x18004cca2  mov     ebx, eax
0x18004cca4  test    eax, eax
0x18004cca6  jns     loc_18004CBD3
0x18004ccac  jmp     short loc_18004CC74
0x18004ccae  lea     rdx, [rdi+1Ch]; pv
0x18004ccb2  mov     r8d, 10h; cb
0x18004ccb8  mov     rcx, rsi; pstm
0x18004ccbb  call    cs:__imp_IStream_Read
0x18004ccc1  mov     ebx, eax
0x18004ccc3  test    eax, eax
0x18004ccc5  jns     loc_18004CBDD
0x18004cccb  jmp     short loc_18004CC74
0x18004cccd  mov     ebx, 80070057h
0x18004ccd2  mov     qword ptr [rdi+8], 0
0x18004ccda  jmp     short loc_18004CC69
```
