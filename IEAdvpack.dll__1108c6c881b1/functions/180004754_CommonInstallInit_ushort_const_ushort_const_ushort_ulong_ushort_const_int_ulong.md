# CommonInstallInit(ushort const *,ushort const *,ushort *,ulong,ushort const *,int,ulong)

- ea: `0x180004754`
- end: `0x180004878`
- name: `?CommonInstallInit@@YAJPEBG0PEAGK0HK@Z`
- size: `292`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, int, unsigned int)`
- caller_count: `6`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004880`
- `0x18000c0c0`
- `0x180010050`
- `0x180010710`
- `0x1800108a0`
- `0x180010ac0`

## callees

- `0x1800021dc`
- `0x1800022bc`
- `0x1800045e8`
- `0x180004754`
- `0x1800067dc`
- `0x180008330`
- `0x1800088c4`
- `0x180008a6c`
- `0x18000a61c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004805`
- `KERNEL32!GetLastError` at `0x180004805`

## pseudocode

```c
__int64 __fastcall CommonInstallInit(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned __int16 *a5,
        int a6,
        unsigned int a7)
{
  unsigned __int64 v7; // rbx
  int v11; // ebx
  unsigned int InfInstallSectionName; // eax
  signed int LastError; // eax

  v7 = a4;
  if ( !(unsigned int)CheckOSVersion() )
    return (unsigned int)-2147023746;
  if ( !dword_1800257E0 )
  {
    MsgBox2Param(hWnd, 0x454u, 0, 0, 0x10u, 0);
    return (unsigned int)-2147023746;
  }
  if ( a2 )
    StringCchCopyW(a3, v7, a2);
  else
    *a3 = 0;
  InfInstallSectionName = GetInfInstallSectionName(a1, a3, v7);
  if ( InfInstallSectionName && InfInstallSectionName <= (unsigned int)v7 )
  {
    if ( (unsigned int)LoadSetupLib(a1, a3, a6, a7) )
    {
      v11 = 0;
      if ( dword_1800257F8 || (v11 = MySetupOpenInfFile(a1), v11 >= 0) )
      {
        if ( !a5 || (v11 = SetLDIDs(a1, a3, 0, a5), v11 >= 0) )
        {
          if ( !(unsigned int)IsGoodAdvancedInfVersion(a1) )
            return (unsigned int)-2147023739;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    return (unsigned int)-2147024774;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004754  push    rbx
0x180004756  push    rbp
0x180004757  push    rsi
0x180004758  push    rdi
0x180004759  sub     rsp, 38h
0x18000475d  mov     ebx, r9d
0x180004760  mov     rsi, r8
0x180004763  mov     rbp, rdx
0x180004766  mov     rdi, rcx
0x180004769  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x18000476e  test    eax, eax
0x180004770  jnz     short loc_18000477C
0x180004772  mov     ebx, 8007047Eh
0x180004777  jmp     loc_18000486D
0x18000477c  cmp     cs:dword_1800257E0, 0
0x180004783  jnz     short loc_1800047AE
0x180004785  mov     rcx, cs:hWnd; hWnd
0x18000478c  xor     r9d, r9d; unsigned __int16 *
0x18000478f  mov     [rsp+58h+var_30], 0; unsigned int
0x180004797  xor     r8d, r8d; unsigned __int16 *
0x18000479a  mov     edx, 454h; uID
0x18000479f  mov     [rsp+58h+var_38], 10h; unsigned int
0x1800047a7  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z; MsgBox2Param(HWND__ *,uint,ushort const *,ushort const *,uint,uint)
0x1800047ac  jmp     short loc_180004772
0x1800047ae  test    rbp, rbp
0x1800047b1  jnz     short loc_1800047BA
0x1800047b3  xor     eax, eax
0x1800047b5  mov     [rsi], ax
0x1800047b8  jmp     short loc_1800047C8
0x1800047ba  mov     rdx, rbx; unsigned __int64
0x1800047bd  mov     r8, rbp; unsigned __int16 *
0x1800047c0  mov     rcx, rsi; unsigned __int16 *
0x1800047c3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800047c8  mov     r8d, ebx; unsigned int
0x1800047cb  mov     rdx, rsi; unsigned __int16 *
0x1800047ce  mov     rcx, rdi; lpFileName
0x1800047d1  call    ?GetInfInstallSectionName@@YAKPEBGPEAGK@Z; GetInfInstallSectionName(ushort const *,ushort *,ulong)
0x1800047d6  test    eax, eax
0x1800047d8  jz      loc_180004868
0x1800047de  cmp     eax, ebx
0x1800047e0  ja      loc_180004868
0x1800047e6  mov     r9d, [rsp+58h+arg_30]; unsigned int
0x1800047ee  mov     rdx, rsi; Section
0x1800047f1  mov     r8d, [rsp+58h+arg_28]; int
0x1800047f9  mov     rcx, rdi; unsigned __int16 *
0x1800047fc  call    ?LoadSetupLib@@YAHPEBG0HK@Z; LoadSetupLib(ushort const *,ushort const *,int,ulong)
0x180004801  test    eax, eax
0x180004803  jnz     short loc_18000481C
0x180004805  call    cs:__imp_GetLastError
0x18000480b  mov     ebx, eax
0x18000480d  test    eax, eax
0x18000480f  jle     short loc_18000486D
0x180004811  movzx   ebx, ax
0x180004814  or      ebx, 80070000h
0x18000481a  jmp     short loc_18000486D
0x18000481c  xor     ebx, ebx
0x18000481e  cmp     cs:dword_1800257F8, ebx
0x180004824  jnz     short loc_180004834
0x180004826  mov     rcx, rdi; unsigned __int16 *
0x180004829  call    ?MySetupOpenInfFile@@YAJPEBG@Z; MySetupOpenInfFile(ushort const *)
0x18000482e  mov     ebx, eax
0x180004830  test    eax, eax
0x180004832  js      short loc_18000486D
0x180004834  mov     r9, [rsp+58h+arg_20]; unsigned __int16 *
0x18000483c  test    r9, r9
0x18000483f  jz      short loc_180004855
0x180004841  xor     r8d, r8d; unsigned int
0x180004844  mov     rdx, rsi; unsigned __int16 *
0x180004847  mov     rcx, rdi; unsigned __int16 *
0x18000484a  call    ?SetLDIDs@@YAJPEBG0K0@Z; SetLDIDs(ushort const *,ushort const *,ulong,ushort const *)
0x18000484f  mov     ebx, eax
0x180004851  test    eax, eax
0x180004853  js      short loc_18000486D
0x180004855  mov     rcx, rdi; unsigned __int16 *
0x180004858  call    ?IsGoodAdvancedInfVersion@@YAHPEBG@Z; IsGoodAdvancedInfVersion(ushort const *)
0x18000485d  test    eax, eax
0x18000485f  jnz     short loc_18000486D
0x180004861  mov     ebx, 80070485h
0x180004866  jmp     short loc_18000486D
0x180004868  mov     ebx, 8007007Ah
0x18000486d  mov     eax, ebx
0x18000486f  add     rsp, 38h
0x180004873  pop     rdi
0x180004874  pop     rsi
0x180004875  pop     rbp
0x180004876  pop     rbx
0x180004877  retn
```
