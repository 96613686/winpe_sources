# CEMfObject::Save(IStream *)

- ea: `0x18009dd10`
- end: `0x18009de44`
- name: `?Save@CEMfObject@@UEAAJPEAUIStream@@@Z`
- size: `308`
- prototype: `HRESULT __fastcall(CEMfObject *this, IStream *lpstream)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180052390`
- `0x18009dd10`
- `0x18009e458`
- `0x1800a4c44`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dd62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dd62`
- `GDI32!DeleteDC` at `0x18009dd9f`
- `GDI32!DeleteDC` at `0x18009dda7`
- `GDI32!DeleteDC` at `0x18009dd9f`
- `GDI32!DeleteDC` at `0x18009dda7`
- `GDI32!CreateCompatibleDC` at `0x18009dd54`
- `GDI32!CreateCompatibleDC` at `0x18009dd54`
- `GDI32!GetWinMetaFileBits` at `0x18009dd90`
- `GDI32!GetWinMetaFileBits` at `0x18009dd90`

## pseudocode

```c
HRESULT __fastcall CEMfObject::Save(CEMfObject *this, IStream *lpstream)
{
  HENHMETAFILE__ **p_m_hPres; // rbx
  HDC hdcRef; // rax
  HDC v6; // rdi
  HRESULT result; // eax
  UINT WinMetaFileBits; // esi
  struct IStreamVtbl *lpVtbl; // rax
  unsigned int v10; // edx
  int v11; // r8d
  unsigned int dwBuf[4]; // [rsp+30h] [rbp-38h] BYREF

  p_m_hPres = &this->m_hPres;
  if ( ((unsigned int (__fastcall *)(CEMfObject *))this->lpVtbl[3].Release)(this) || !*p_m_hPres )
  {
    WinMetaFileBits = 0;
  }
  else
  {
    hdcRef = CreateCompatibleDC(0);
    v6 = hdcRef;
    if ( !hdcRef )
      goto LABEL_4;
    WinMetaFileBits = GetWinMetaFileBits(*p_m_hPres, 0, 0, 8, hdcRef);
    if ( !WinMetaFileBits )
    {
      DeleteDC(v6);
LABEL_4:
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
      return result;
    }
    DeleteDC(v6);
  }
  dwBuf[1] = this->m_lWidth;
  dwBuf[2] = this->m_lHeight;
  lpVtbl = lpstream->lpVtbl;
  dwBuf[0] = 0;
  dwBuf[3] = WinMetaFileBits;
  result = ((__int64 (__fastcall *)(IStream *, unsigned int *, __int64))lpVtbl->Write)(lpstream, dwBuf, 16);
  if ( result >= 0 )
  {
    if ( ((unsigned int (__fastcall *)(CEMfObject *))this->lpVtbl[3].Release)(this) || !*p_m_hPres )
    {
      StSetSize(lpstream, v10, v11);
      return 0;
    }
    else
    {
      return UtHEMFToEMFStm(*p_m_hPres, WinMetaFileBits, lpstream, WRITE_AS_WMF);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18009dd10  mov     [rsp+arg_10], rbx
0x18009dd15  mov     [rsp+arg_18], rsi
0x18009dd1a  push    rdi
0x18009dd1b  push    r14
0x18009dd1d  push    r15
0x18009dd1f  sub     rsp, 50h
0x18009dd23  mov     rax, cs:__security_cookie
0x18009dd2a  xor     rax, rsp
0x18009dd2d  mov     [rsp+68h+var_28], rax
0x18009dd32  mov     rax, [this]
0x18009dd35  lea     rbx, [this+10h]
0x18009dd39  mov     r15, lpstream
0x18009dd3c  mov     r14, this
0x18009dd3f  mov     rax, [rax+58h]
0x18009dd43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dd48  test    eax, eax
0x18009dd4a  jnz     short loc_18009DDAF
0x18009dd4c  cmp     qword ptr [rbx], 0
0x18009dd50  jz      short loc_18009DDAF
0x18009dd52  xor     ecx, ecx; hdc
0x18009dd54  call    cs:__imp_CreateCompatibleDC
0x18009dd5a  mov     rdi, rax
0x18009dd5d  test    rax, rax
0x18009dd60  jnz     short loc_18009DD7D
0x18009dd62  call    cs:__imp_GetLastError
0x18009dd68  test    eax, eax
0x18009dd6a  jle     loc_18009DE21
0x18009dd70  movzx   eax, ax
0x18009dd73  or      eax, 80070000h
0x18009dd78  jmp     loc_18009DE21
0x18009dd7d  mov     this, [rbx]; hemf
0x18009dd80  mov     r9d, 8; iMapMode
0x18009dd86  xor     r8d, r8d; pData16
0x18009dd89  mov     [rsp+68h+hdcRef], rdi; hdcRef
0x18009dd8e  xor     edx, edx; cbData16
0x18009dd90  call    cs:__imp_GetWinMetaFileBits
0x18009dd96  mov     esi, eax
0x18009dd98  mov     this, rdi; hdc
0x18009dd9b  test    eax, eax
0x18009dd9d  jnz     short loc_18009DDA7
0x18009dd9f  call    cs:__imp_DeleteDC
0x18009dda5  jmp     short loc_18009DD62
0x18009dda7  call    cs:__imp_DeleteDC
0x18009ddad  jmp     short loc_18009DDB1
0x18009ddaf  xor     esi, esi
0x18009ddb1  mov     eax, [r14+40h]
0x18009ddb5  lea     lpstream, [rsp+68h+dwBuf]
0x18009ddba  mov     [rsp+68h+dwBuf+4], eax
0x18009ddbe  xor     r9d, r9d
0x18009ddc1  mov     eax, [r14+44h]
0x18009ddc5  mov     this, r15
0x18009ddc8  mov     [rsp+68h+dwBuf+8], eax
0x18009ddcc  mov     rax, [r15]
0x18009ddcf  lea     r8d, [r9+10h]
0x18009ddd3  mov     [rsp+68h+dwBuf], 0
0x18009dddb  mov     [rsp+68h+dwBuf+0Ch], esi
0x18009dddf  mov     rax, [rax+20h]
0x18009dde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009dde8  test    eax, eax
0x18009ddea  js      short loc_18009DE21
0x18009ddec  mov     rax, [r14]
0x18009ddef  mov     this, r14
0x18009ddf2  mov     rax, [rax+58h]
0x18009ddf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ddfb  test    eax, eax
0x18009ddfd  jnz     short loc_18009DE17
0x18009ddff  mov     this, [rbx]; hEMF
0x18009de02  test    this, this
0x18009de05  jz      short loc_18009DE17
0x18009de07  lea     r9d, [rax+0Dh]; emfwType
0x18009de0b  mov     r8, r15; lpstream
0x18009de0e  mov     edx, esi; dwSize
0x18009de10  call    ?UtHEMFToEMFStm@@YAJPEAUHENHMETAFILE__@@KPEAUIStream@@W4tagEMFWRITETYPE@@@Z; UtHEMFToEMFStm(HENHMETAFILE__ *,ulong,IStream *,tagEMFWRITETYPE)
0x18009de15  jmp     short loc_18009DE21
0x18009de17  mov     this, r15; pstm
0x18009de1a  call    ?StSetSize@@YAJPEAUIStream@@KH@Z; StSetSize(IStream *,ulong,int)
0x18009de1f  xor     eax, eax
0x18009de21  mov     this, [rsp+68h+var_28]
0x18009de26  xor     this, rsp; StackCookie
0x18009de29  call    __security_check_cookie
0x18009de2e  lea     r11, [rsp+68h+var_18]
0x18009de33  mov     rbx, [r11+30h]
0x18009de37  mov     rsi, [r11+38h]
0x18009de3b  mov     rsp, r11
0x18009de3e  pop     r15
0x18009de40  pop     r14
0x18009de42  pop     rdi
0x18009de43  retn
```
