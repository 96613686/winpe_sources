# PlayMetaFileBands(PrinterBase *,HWND__ *,HMETAFILE__ *)

- ea: `0x18003cc44`
- end: `0x18003cdc4`
- name: `?PlayMetaFileBands@@YAIPEAVPrinterBase@@PEAUHWND__@@PEAUHMETAFILE__@@@Z`
- size: `384`
- prototype: `unsigned int __fastcall(struct PrinterBase *, HWND, HMETAFILE)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003c7f0`

## callees

- `0x18003cc44`
- `0x18003cdcc`
- `0x18003cfec`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!IsRectEmpty` at `0x18003ccbc`
- `USER32!IsRectEmpty` at `0x18003ccbc`
- `GDI32!GetDeviceCaps` at `0x18003cc7a`
- `GDI32!GetDeviceCaps` at `0x18003cc7a`
- `GDI32!Escape` at `0x18003cd5f`
- `GDI32!Escape` at `0x18003cd5f`
- `GDI32!PlayMetaFile` at `0x18003cd30`
- `GDI32!PlayMetaFile` at `0x18003cd30`
- `GDI32!SelectClipRgn` at `0x18003cd1f`
- `GDI32!SelectClipRgn` at `0x18003cd1f`
- `GDI32!CreateRectRgnIndirect` at `0x18003cd06`
- `GDI32!CreateRectRgnIndirect` at `0x18003cd06`
- `GDI32!DeleteObject` at `0x18003cd3d`
- `GDI32!DeleteObject` at `0x18003cda3`
- `GDI32!DeleteObject` at `0x18003cd3d`
- `GDI32!DeleteObject` at `0x18003cda3`

## pseudocode

```c
__int64 __fastcall PlayMetaFileBands(HDC *a1, HWND a2, HMETAFILE a3)
{
  HRGN v7; // rax
  HRGN v8; // rdi
  int v9; // edi
  unsigned int v10; // ebx
  RECT rc; // [rsp+30h] [rbp-38h] BYREF

  if ( (GetDeviceCaps(a1[1], 38) & 1) == 0 || (*((int (__fastcall **)(HDC *))*a1 + 5))(a1) <= 0 )
    return 486;
  do
  {
    v9 = Escape(a1[1], 3, 0, 0, &rc);
    if ( v9 <= 0 || IsRectEmpty(&rc) || dword_1803F9D48 || (AbortProc(a1[1], 0), dword_1803F9D48) )
    {
      (*((void (__fastcall **)(HDC *))*a1 + 4))(a1);
      if ( !dword_1803F9D48 && v9 > 0 )
        return 0;
      return 486;
    }
    if ( !(unsigned int)ScaleFormPrint((struct PrinterBase *)a1, a2) )
      return 482;
    v7 = CreateRectRgnIndirect(&rc);
    v8 = v7;
    if ( !v7 )
      return 7;
    if ( !SelectClipRgn(a1[1], v7) )
    {
      v10 = 7;
      goto LABEL_18;
    }
    if ( !PlayMetaFile(a1[1], a3) )
    {
      v10 = 482;
LABEL_18:
      DeleteObject(v8);
      return v10;
    }
  }
  while ( DeleteObject(v8) );
  return 482;
}

```

## disassembly

```asm
0x18003cc44  mov     [rsp+arg_18], rbx
0x18003cc49  push    rbp
0x18003cc4a  push    rsi
0x18003cc4b  push    rdi
0x18003cc4c  mov     eax, 50h
0x18003cc51  call    _alloca_probe
0x18003cc56  sub     rsp, rax
0x18003cc59  mov     rax, cs:__security_cookie
0x18003cc60  xor     rax, rsp
0x18003cc63  mov     [rsp+68h+var_28], rax
0x18003cc68  mov     rbx, rcx
0x18003cc6b  mov     rcx, [rcx+8]; hdc
0x18003cc6f  mov     rsi, rdx
0x18003cc72  mov     edx, 26h ; '&'; index
0x18003cc77  mov     rbp, r8
0x18003cc7a  call    cs:__imp_GetDeviceCaps
0x18003cc80  test    al, 1
0x18003cc82  jz      short loc_18003CC95
0x18003cc84  mov     rax, [rbx]
0x18003cc87  mov     rcx, rbx
0x18003cc8a  call    qword ptr [rax+28h]
0x18003cc8d  test    eax, eax
0x18003cc8f  jg      loc_18003CD47
0x18003cc95  mov     eax, 1E6h
0x18003cc9a  mov     rcx, [rsp+68h+var_28]
0x18003cc9f  xor     rcx, rsp; StackCookie
0x18003cca2  call    __security_check_cookie
0x18003cca7  mov     rbx, [rsp+68h+arg_18]
0x18003ccaf  add     rsp, 50h
0x18003ccb3  pop     rdi
0x18003ccb4  pop     rsi
0x18003ccb5  pop     rbp
0x18003ccb6  retn
0x18003ccb7  lea     rcx, [rsp+68h+rc]; lprc
0x18003ccbc  call    cs:__imp_IsRectEmpty
0x18003ccc2  test    eax, eax
0x18003ccc4  jnz     loc_18003CD6F
0x18003ccca  cmp     cs:dword_1803F9D48, eax
0x18003ccd0  jnz     loc_18003CD6F
0x18003ccd6  mov     rcx, [rbx+8]; HDC
0x18003ccda  xor     edx, edx; int
0x18003ccdc  call    ?AbortProc@@YAHPEAUHDC__@@H@Z; AbortProc(HDC__ *,int)
0x18003cce1  cmp     cs:dword_1803F9D48, 0
0x18003cce8  jnz     loc_18003CD6F
0x18003ccee  mov     rdx, rsi; HWND
0x18003ccf1  mov     rcx, rbx; struct PrinterBase *
0x18003ccf4  call    ?ScaleFormPrint@@YAHPEAVPrinterBase@@PEAUHWND__@@@Z; ScaleFormPrint(PrinterBase *,HWND__ *)
0x18003ccf9  test    eax, eax
0x18003ccfb  jz      loc_18003CDBA
0x18003cd01  lea     rcx, [rsp+68h+rc]; lprect
0x18003cd06  call    cs:__imp_CreateRectRgnIndirect
0x18003cd0c  mov     rdi, rax
0x18003cd0f  test    rax, rax
0x18003cd12  jz      loc_18003CDB0
0x18003cd18  mov     rcx, [rbx+8]; hdc
0x18003cd1c  mov     rdx, rax; hrgn
0x18003cd1f  call    cs:__imp_SelectClipRgn
0x18003cd25  test    eax, eax
0x18003cd27  jz      short loc_18003CD9B
0x18003cd29  mov     rcx, [rbx+8]; hdc
0x18003cd2d  mov     rdx, rbp; hmf
0x18003cd30  call    cs:__imp_PlayMetaFile
0x18003cd36  test    eax, eax
0x18003cd38  jz      short loc_18003CD94
0x18003cd3a  mov     rcx, rdi; ho
0x18003cd3d  call    cs:__imp_DeleteObject
0x18003cd43  test    eax, eax
0x18003cd45  jz      short loc_18003CDBA
0x18003cd47  mov     rcx, [rbx+8]; hdc
0x18003cd4b  xor     r9d, r9d; pvIn
0x18003cd4e  lea     rax, [rsp+68h+rc]
0x18003cd53  lea     edx, [r9+3]; iEscape
0x18003cd57  xor     r8d, r8d; cjIn
0x18003cd5a  mov     [rsp+68h+pvOut], rax; pvOut
0x18003cd5f  call    cs:__imp_Escape
0x18003cd65  mov     edi, eax
0x18003cd67  test    eax, eax
0x18003cd69  jg      loc_18003CCB7
0x18003cd6f  mov     rax, [rbx]
0x18003cd72  mov     rcx, rbx
0x18003cd75  call    qword ptr [rax+20h]
0x18003cd78  cmp     cs:dword_1803F9D48, 0
0x18003cd7f  jnz     loc_18003CC95
0x18003cd85  test    edi, edi
0x18003cd87  jle     loc_18003CC95
0x18003cd8d  xor     eax, eax
0x18003cd8f  jmp     loc_18003CC9A
0x18003cd94  mov     ebx, 1E2h
0x18003cd99  jmp     short loc_18003CDA0
0x18003cd9b  mov     ebx, 7
0x18003cda0  mov     rcx, rdi; ho
0x18003cda3  call    cs:__imp_DeleteObject
0x18003cda9  mov     eax, ebx
0x18003cdab  jmp     loc_18003CC9A
0x18003cdb0  mov     eax, 7
0x18003cdb5  jmp     loc_18003CC9A
0x18003cdba  mov     eax, 1E2h
0x18003cdbf  jmp     loc_18003CC9A
```
