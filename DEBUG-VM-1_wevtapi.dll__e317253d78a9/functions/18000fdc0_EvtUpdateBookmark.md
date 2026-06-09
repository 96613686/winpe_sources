# EvtUpdateBookmark

- ea: `0x18000fdc0`
- end: `0x18000fe7a`
- name: `EvtUpdateBookmark`
- size: `186`
- prototype: `BOOL __stdcall(EVT_HANDLE Bookmark, EVT_HANDLE Event)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180006870`
- `0x180006aec`
- `0x18000fdc0`
- `0x18000ff68`
- `0x180011394`
- `0x18001148c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000fe4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __stdcall EvtUpdateBookmark(EVT_HANDLE Bookmark, EVT_HANDLE Event)
{
  BOOL v4; // edi
  __int64 v5; // rcx
  DWORD ReferencedObjectAs; // eax
  __int64 v7; // rcx
  DWORD v8; // r14d
  wmi::RefBase *v9; // rsi
  wmi::RefBase *v10; // rbx
  _WORD *v11; // rax
  EvtException *v13; // [rsp+20h] [rbp-28h] BYREF
  wmi::RefBase *v14; // [rsp+60h] [rbp+18h] BYREF
  wmi::RefBase *v15; // [rsp+68h] [rbp+20h] BYREF

  LastErrInfo::Reset((LastErrInfo *)Bookmark);
  v4 = 0;
  v14 = 0;
  ReferencedObjectAs = ObjectTable::GetReferencedObjectAsType<BookmarkObject,void>(v5, Bookmark, &v14);
  try
  {
    v8 = ReferencedObjectAs;
    if ( ReferencedObjectAs )
    {
      v9 = v14;
    }
    else
    {
      v15 = 0;
      v8 = ObjectTable::GetReferencedObjectAsType<Event,void>(v7, Event, &v15);
      v9 = v14;
      v10 = v15;
      if ( !v8 )
      {
        Bookmark::CopyFrom((wmi::RefBase *)((char *)v14 + 64), (wmi::RefBase *)((char *)v15 + 104));
        v11 = (_WORD *)*((_QWORD *)v9 + 4);
        *((_QWORD *)v9 + 5) = v11;
        *v11 = 0;
      }
      if ( v10 )
        wmi::RefBase::Release(v10);
    }
    if ( v9 )
      wmi::RefBase::Release(v9);
  }
  catch ( EvtException *v13 )
  {
    LODWORD(v14) = *((_DWORD *)v13 + 6);
    v4 = 0;
    v8 = (unsigned int)v14;
  }
  SetLastError(v8);
  LOBYTE(v4) = v8 == 0;
  return v4;
}

```

## disassembly

```asm
0x18000fdc0  mov     [rsp+arg_0], rbx
0x18000fdc5  push    rsi
0x18000fdc6  push    rdi
0x18000fdc7  push    r14
0x18000fdc9  sub     rsp, 30h
0x18000fdcd  mov     rbx, rdx
0x18000fdd0  mov     rsi, rcx
0x18000fdd3  call    ?Reset@LastErrInfo@@QEAAXXZ; LastErrInfo::Reset(void)
0x18000fdd8  xor     edi, edi
0x18000fdda  mov     [rsp+48h+arg_10], rdi
0x18000fddf  lea     r8, [rsp+48h+arg_10]
0x18000fde4  mov     rdx, rsi
0x18000fde7  call    ??$GetReferencedObjectAsType@VBookmarkObject@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VBookmarkObject@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<BookmarkObject,void>(void *,wmi::AutoRef<BookmarkObject> &)
0x18000fdec  mov     r14d, eax
0x18000fdef  test    eax, eax
0x18000fdf1  jnz     short loc_18000FE6A
0x18000fdf3  mov     [rsp+48h+arg_18], rdi
0x18000fdf8  lea     r8, [rsp+48h+arg_18]
0x18000fdfd  mov     rdx, rbx
0x18000fe00  call    ??$GetReferencedObjectAsType@VEvent@@X@ObjectTable@@QEAAKPEAXAEAV?$AutoRef@VEvent@@@wmi@@@Z; ObjectTable::GetReferencedObjectAsType<Event,void>(void *,wmi::AutoRef<Event> &)
0x18000fe05  mov     r14d, eax
0x18000fe08  mov     rsi, [rsp+48h+arg_10]
0x18000fe0d  mov     rbx, [rsp+48h+arg_18]
0x18000fe12  test    eax, eax
0x18000fe14  jnz     short loc_18000FE2E
0x18000fe16  lea     rdx, [rbx+68h]; struct Bookmark *
0x18000fe1a  lea     rcx, [rsi+40h]; this
0x18000fe1e  call    ?CopyFrom@Bookmark@@QEAAXAEBV1@@Z; Bookmark::CopyFrom(Bookmark const &)
0x18000fe23  mov     rax, [rsi+20h]
0x18000fe27  mov     [rsi+28h], rax
0x18000fe2b  mov     [rax], di
0x18000fe2e  test    rbx, rbx
0x18000fe31  jz      short loc_18000FE3C
0x18000fe33  mov     rcx, rbx; this
0x18000fe36  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000fe3b  nop
0x18000fe3c  test    rsi, rsi
0x18000fe3f  jz      short loc_18000FE4A
0x18000fe41  mov     rcx, rsi; this
0x18000fe44  call    ?Release@RefBase@wmi@@QEAAKXZ; wmi::RefBase::Release(void)
0x18000fe49  nop
0x18000fe4a  mov     ecx, r14d; dwErrCode
0x18000fe4d  call    cs:__imp_SetLastError
0x18000fe53  test    r14d, r14d
0x18000fe56  setz    dil
0x18000fe5a  mov     eax, edi
0x18000fe5c  mov     rbx, [rsp+48h+arg_0]
0x18000fe61  add     rsp, 30h
0x18000fe65  pop     r14
0x18000fe67  pop     rdi
0x18000fe68  pop     rsi
0x18000fe69  retn
0x18000fe6a  mov     rsi, [rsp+48h+arg_10]
0x18000fe6f  jmp     short loc_18000FE3C
0x18000fe71  xor     edi, edi
0x18000fe73  mov     r14d, dword ptr [rsp+48h+arg_10]
0x18000fe78  jmp     short loc_18000FE4A
```
