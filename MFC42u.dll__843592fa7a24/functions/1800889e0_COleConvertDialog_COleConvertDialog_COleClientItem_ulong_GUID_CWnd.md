# COleConvertDialog::COleConvertDialog(COleClientItem *,ulong,_GUID *,CWnd *)

- ea: `0x1800889e0`
- end: `0x180088b88`
- name: `??0COleConvertDialog@@QEAA@PEAVCOleClientItem@@KPEAU_GUID@@PEAVCWnd@@@Z`
- size: `424`
- prototype: `COleConvertDialog *(COleConvertDialog *__hidden this, struct COleClientItem *, unsigned int, struct _GUID *, struct CWnd *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009cb00`

## callees

- `0x180014420`
- `0x180031f00`
- `0x180056140`
- `0x1800818e0`
- `0x1800889e0`
- `0x18008a990`
- `0x1800d1f92`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180088b3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180088b3d`
- `OLE32!ReadFmtUserTypeStg` at `0x180088ad7`
- `OLE32!ReadFmtUserTypeStg` at `0x180088ad7`
- `OLE32!OleRegGetUserType` at `0x180088b27`
- `OLE32!OleRegGetUserType` at `0x180088b27`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x180088ab1`
- `api-ms-win-core-com-l2-1-1!ReadClassStg` at `0x180088ab1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
COleConvertDialog *__fastcall COleConvertDialog::COleConvertDialog(
        COleConvertDialog *this,
        struct COleClientItem *a2,
        int a3,
        struct _GUID *a4,
        struct CWnd *a5)
{
  int v9; // ecx
  LPOLESTR v10; // rbx
  WCHAR *v11; // rax
  LPOLESTR lpszUserType; // [rsp+58h] [rbp+10h] BYREF
  CLIPFORMAT pcf; // [rsp+60h] [rbp+18h] BYREF

  COleDialog::COleDialog(this, a5);
  *(_QWORD *)this = &COleConvertDialog::`vftable';
  memset_0((char *)this + 200, 0, 0xC0u);
  if ( a4 )
    *(struct _GUID *)((char *)this + 264) = *a4;
  *((_DWORD *)this + 50) = 192;
  *((_DWORD *)this + 51) = a3;
  if ( !dword_180131A40 && (unsigned int)AfxHelpEnabled() )
    *((_DWORD *)this + 51) |= 1u;
  *((_QWORD *)this + 28) = AfxOleHookProc;
  *((_DWORD *)this + 32) = 30726;
  if ( a2 )
  {
    v9 = *((_DWORD *)a2 + 37);
    *((_DWORD *)this + 84) = v9 == 1;
    *((_DWORD *)this + 82) = *((_DWORD *)a2 + 23);
    if ( !a4 )
    {
      if ( v9 == 1 )
        goto LABEL_12;
      if ( !ReadClassStg(*((LPSTORAGE *)a2 + 13), (CLSID *)((char *)this + 264)) )
        a4 = (struct _GUID *)((char *)this + 264);
      pcf = 0;
      lpszUserType = 0;
      ReadFmtUserTypeStg(*((LPSTORAGE *)a2 + 13), &pcf, &lpszUserType);
      *((_QWORD *)this + 44) = lpszUserType;
      *((_WORD *)this + 166) = pcf;
      if ( !a4 )
LABEL_12:
        COleClientItem::GetClassID(a2, (struct _GUID *)((char *)this + 264));
    }
    if ( !*((_QWORD *)this + 44) )
    {
      lpszUserType = 0;
      if ( OleRegGetUserType((const IID *const)((char *)this + 264), 1u, &lpszUserType) )
      {
        v11 = (WCHAR *)CoTaskMemAlloc(0x200u);
        v10 = v11;
        if ( v11 )
        {
          *(_DWORD *)v11 = 63;
          AfxLoadString(0xF095u, v11, 0x100u);
        }
      }
      else
      {
        v10 = lpszUserType;
      }
      *((_QWORD *)this + 44) = v10;
    }
    *((_QWORD *)this + 43) = COleClientItem::GetIconicMetafile(a2);
  }
  return this;
}

```

## disassembly

```asm
0x1800889e0  mov     [rsp+arg_0], rcx
0x1800889e5  push    rbx
0x1800889e6  push    rbp
0x1800889e7  push    rsi
0x1800889e8  push    rdi
0x1800889e9  push    r14
0x1800889eb  sub     rsp, 20h
0x1800889ef  mov     rbp, r9
0x1800889f2  mov     ebx, r8d
0x1800889f5  mov     rsi, rdx
0x1800889f8  mov     rdi, rcx
0x1800889fb  mov     rdx, [rsp+48h+arg_20]; struct CWnd *
0x180088a00  call    ??0COleDialog@@QEAA@PEAVCWnd@@@Z; COleDialog::COleDialog(CWnd *)
0x180088a05  nop
0x180088a06  lea     rax, ??_7COleConvertDialog@@6B@; const COleConvertDialog::`vftable'
0x180088a0d  mov     [rdi], rax
0x180088a10  lea     r14, [rdi+0C8h]
0x180088a17  xor     edx, edx; Val
0x180088a19  mov     r8d, 0C0h; Size
0x180088a1f  mov     rcx, r14; void *
0x180088a22  call    memset_0
0x180088a27  test    rbp, rbp
0x180088a2a  jz      short loc_180088A38
0x180088a2c  movups  xmm0, xmmword ptr [rbp+0]
0x180088a30  movdqu  xmmword ptr [rdi+108h], xmm0
0x180088a38  mov     dword ptr [r14], 0C0h
0x180088a3f  mov     [rdi+0CCh], ebx
0x180088a45  cmp     cs:dword_180131A40, 0
0x180088a4c  jnz     short loc_180088A5E
0x180088a4e  call    ?AfxHelpEnabled@@YAHXZ; AfxHelpEnabled(void)
0x180088a53  test    eax, eax
0x180088a55  jz      short loc_180088A5E
0x180088a57  or      dword ptr [rdi+0CCh], 1
0x180088a5e  lea     rax, ?AfxOleHookProc@@YAIPEAUHWND__@@I_K_J@Z; AfxOleHookProc(HWND__ *,uint,unsigned __int64,__int64)
0x180088a65  mov     [rdi+0E0h], rax
0x180088a6c  mov     dword ptr [rdi+80h], 7806h
0x180088a76  test    rsi, rsi
0x180088a79  jz      loc_180088B7A
0x180088a7f  mov     ecx, [rsi+94h]
0x180088a85  xor     eax, eax
0x180088a87  cmp     ecx, 1
0x180088a8a  setz    al
0x180088a8d  mov     [rdi+150h], eax
0x180088a93  mov     eax, [rsi+5Ch]
0x180088a96  mov     [rdi+148h], eax
0x180088a9c  test    rbp, rbp
0x180088a9f  jnz     short loc_180088B06
0x180088aa1  cmp     ecx, 1
0x180088aa4  jz      short loc_180088AFA
0x180088aa6  lea     rbx, [r14+40h]
0x180088aaa  mov     rdx, rbx; pclsid
0x180088aad  mov     rcx, [rsi+68h]; pStg
0x180088ab1  call    cs:__imp_ReadClassStg
0x180088ab7  test    eax, eax
0x180088ab9  cmovz   rbp, rbx
0x180088abd  xor     eax, eax
0x180088abf  mov     [rsp+48h+pcf], ax
0x180088ac4  mov     [rsp+48h+lpszUserType], rax
0x180088ac9  lea     r8, [rsp+48h+lpszUserType]; lplpszUserType
0x180088ace  lea     rdx, [rsp+48h+pcf]; pcf
0x180088ad3  mov     rcx, [rsi+68h]; pstg
0x180088ad7  call    cs:__imp_ReadFmtUserTypeStg
0x180088add  mov     rax, [rsp+48h+lpszUserType]
0x180088ae2  mov     [rdi+160h], rax
0x180088ae9  movzx   eax, [rsp+48h+pcf]
0x180088aee  mov     [rdi+14Ch], ax
0x180088af5  test    rbp, rbp
0x180088af8  jnz     short loc_180088B06
0x180088afa  lea     rdx, [r14+40h]; struct _GUID *
0x180088afe  mov     rcx, rsi; this
0x180088b01  call    ?GetClassID@COleClientItem@@QEBAXPEAU_GUID@@@Z; COleClientItem::GetClassID(_GUID *)
0x180088b06  cmp     qword ptr [rdi+160h], 0
0x180088b0e  jnz     short loc_180088B6B
0x180088b10  mov     [rsp+48h+lpszUserType], 0
0x180088b19  lea     rcx, [r14+40h]; clsid
0x180088b1d  lea     r8, [rsp+48h+lpszUserType]; pszUserType
0x180088b22  mov     edx, 1; dwFormOfType
0x180088b27  call    cs:__imp_OleRegGetUserType
0x180088b2d  test    eax, eax
0x180088b2f  jnz     short loc_180088B38
0x180088b31  mov     rbx, [rsp+48h+lpszUserType]
0x180088b36  jmp     short loc_180088B64
0x180088b38  mov     ecx, 200h; cb
0x180088b3d  call    cs:__imp_CoTaskMemAlloc
0x180088b43  mov     rbx, rax
0x180088b46  test    rax, rax
0x180088b49  jz      short loc_180088B64
0x180088b4b  mov     dword ptr [rax], 3Fh ; '?'
0x180088b51  mov     r8d, 100h; cchBufferMax
0x180088b57  mov     rdx, rax; lpBuffer
0x180088b5a  mov     ecx, 0F095h; uID
0x180088b5f  call    ?AfxLoadString@@YAHIPEAGI@Z; AfxLoadString(uint,ushort *,uint)
0x180088b64  mov     [rdi+160h], rbx
0x180088b6b  mov     rcx, rsi; this
0x180088b6e  call    ?GetIconicMetafile@COleClientItem@@QEAAPEAXXZ; COleClientItem::GetIconicMetafile(void)
0x180088b73  mov     [rdi+158h], rax
0x180088b7a  mov     rax, rdi
0x180088b7d  add     rsp, 20h
0x180088b81  pop     r14
0x180088b83  pop     rdi
0x180088b84  pop     rsi
0x180088b85  pop     rbp
0x180088b86  pop     rbx
0x180088b87  retn
```
