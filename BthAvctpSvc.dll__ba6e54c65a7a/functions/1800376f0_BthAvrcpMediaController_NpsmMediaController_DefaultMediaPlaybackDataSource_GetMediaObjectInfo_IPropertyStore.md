# BthAvrcpMediaController::NpsmMediaController::DefaultMediaPlaybackDataSource::GetMediaObjectInfo(IPropertyStore * *)

- ea: `0x1800376f0`
- end: `0x180037848`
- name: `?GetMediaObjectInfo@DefaultMediaPlaybackDataSource@NpsmMediaController@BthAvrcpMediaController@@UEAAJPEAPEAUIPropertyStore@@@Z`
- size: `344`
- prototype: `__int64 __fastcall(BthAvrcpMediaController::NpsmMediaController::DefaultMediaPlaybackDataSource *__hidden this, struct IPropertyStore **)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800376f0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037747`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180037747`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180037729`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180037729`

## pseudocode

```c
HRESULT __fastcall BthAvrcpMediaController::NpsmMediaController::DefaultMediaPlaybackDataSource::GetMediaObjectInfo(
        BthAvrcpMediaController::NpsmMediaController::DefaultMediaPlaybackDataSource *this,
        struct IPropertyStore **a2)
{
  HRESULT result; // eax
  _WORD *v4; // rax
  __int128 v5; // [rsp+20h] [rbp-20h] BYREF
  __int64 v6; // [rsp+30h] [rbp-10h]
  void *ppv; // [rsp+58h] [rbp+18h] BYREF

  if ( !a2 )
    return -2147467261;
  *a2 = 0;
  ppv = 0;
  result = PSCreateMemoryPropertyStore(&IID_IPropertyStore, &ppv);
  if ( result >= 0 )
  {
    *(_QWORD *)&v5 = 0;
    v6 = 0;
    v4 = CoTaskMemAlloc(2u);
    *((_QWORD *)&v5 + 1) = v4;
    if ( v4 )
    {
      *v4 = 0;
      LOWORD(v5) = 31;
    }
    else
    {
      v5 = 0;
      v6 = 0;
    }
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(ppv, &PKEY_Title, &v5);
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
      ppv,
      &PKEY_Music_Artist,
      &v5);
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
      ppv,
      &PKEY_Music_AlbumTitle,
      &v5);
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
      ppv,
      &PKEY_Music_Genre,
      &v5);
    DWORD2(v5) = 0;
    LOWORD(v5) = 19;
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
      ppv,
      &PKEY_Music_TrackNumber,
      &v5);
    *((_QWORD *)&v5 + 1) = 0;
    LOWORD(v5) = 21;
    (*(void (__fastcall **)(void *, const PROPERTYKEY *, __int128 *))(*(_QWORD *)ppv + 48LL))(
      ppv,
      &PKEY_Media_Duration,
      &v5);
    *a2 = (struct IPropertyStore *)ppv;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800376f0  mov     [rsp-8+arg_0], rbx
0x1800376f5  push    rbp
0x1800376f6  mov     rbp, rsp
0x1800376f9  sub     rsp, 40h
0x1800376fd  mov     rbx, rdx
0x180037700  test    rdx, rdx
0x180037703  jnz     short loc_18003770F
0x180037705  mov     eax, 80004003h
0x18003770a  jmp     loc_18003783D
0x18003770f  mov     qword ptr [rdx], 0
0x180037716  lea     rcx, IID_IPropertyStore; riid
0x18003771d  lea     rdx, [rbp+ppv]; ppv
0x180037721  mov     [rbp+ppv], 0
0x180037729  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003772f  test    eax, eax
0x180037731  js      loc_18003783D
0x180037737  xor     eax, eax
0x180037739  xorps   xmm0, xmm0
0x18003773c  movups  [rbp+var_20], xmm0
0x180037740  mov     [rbp+var_10], rax
0x180037744  lea     ecx, [rax+2]; cb
0x180037747  call    cs:__imp_CoTaskMemAlloc
0x18003774d  mov     qword ptr [rbp+var_20+8], rax
0x180037751  test    rax, rax
0x180037754  jz      short loc_180037764
0x180037756  xor     ecx, ecx
0x180037758  mov     [rax], cx
0x18003775b  lea     eax, [rcx+1Fh]
0x18003775e  mov     word ptr [rbp+var_20], ax
0x180037762  jmp     short loc_180037771
0x180037764  xorps   xmm0, xmm0
0x180037767  xor     eax, eax
0x180037769  movups  [rbp+var_20], xmm0
0x18003776d  mov     [rbp+var_10], rax
0x180037771  mov     rcx, [rbp+ppv]
0x180037775  lea     r8, [rbp+var_20]
0x180037779  lea     rdx, PKEY_Title
0x180037780  mov     rax, [rcx]
0x180037783  mov     rax, [rax+30h]
0x180037787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003778c  mov     rcx, [rbp+ppv]
0x180037790  lea     r8, [rbp+var_20]
0x180037794  lea     rdx, PKEY_Music_Artist
0x18003779b  mov     rax, [rcx]
0x18003779e  mov     rax, [rax+30h]
0x1800377a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377a7  mov     rcx, [rbp+ppv]
0x1800377ab  lea     r8, [rbp+var_20]
0x1800377af  lea     rdx, PKEY_Music_AlbumTitle
0x1800377b6  mov     rax, [rcx]
0x1800377b9  mov     rax, [rax+30h]
0x1800377bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377c2  mov     rcx, [rbp+ppv]
0x1800377c6  lea     r8, [rbp+var_20]
0x1800377ca  lea     rdx, PKEY_Music_Genre
0x1800377d1  mov     rax, [rcx]
0x1800377d4  mov     rax, [rax+30h]
0x1800377d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800377dd  mov     rcx, [rbp+ppv]
0x1800377e1  lea     r8, [rbp+var_20]
0x1800377e5  mov     eax, 13h
0x1800377ea  mov     dword ptr [rbp+var_20+8], 0
0x1800377f1  mov     word ptr [rbp+var_20], ax
0x1800377f5  lea     rdx, PKEY_Music_TrackNumber
0x1800377fc  mov     rax, [rcx]
0x1800377ff  mov     rax, [rax+30h]
0x180037803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037808  mov     rcx, [rbp+ppv]
0x18003780c  lea     r8, [rbp+var_20]
0x180037810  mov     eax, 15h
0x180037815  mov     qword ptr [rbp+var_20+8], 0
0x18003781d  mov     word ptr [rbp+var_20], ax
0x180037821  lea     rdx, PKEY_Media_Duration
0x180037828  mov     rax, [rcx]
0x18003782b  mov     rax, [rax+30h]
0x18003782f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037834  mov     rax, [rbp+ppv]
0x180037838  mov     [rbx], rax
0x18003783b  xor     eax, eax
0x18003783d  mov     rbx, [rsp+40h+arg_0]
0x180037842  add     rsp, 40h
0x180037846  pop     rbp
0x180037847  retn
```
