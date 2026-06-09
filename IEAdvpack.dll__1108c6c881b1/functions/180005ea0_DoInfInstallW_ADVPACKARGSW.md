# DoInfInstallW(_ADVPACKARGSW *)

- ea: `0x180005ea0`
- end: `0x180005f79`
- name: `?DoInfInstallW@@YAJPEAU_ADVPACKARGSW@@@Z`
- size: `217`
- prototype: `__int64 __fastcall(struct _ADVPACKARGSW *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180005dc0`

## callees

- `0x180003ce0`
- `0x180003e20`
- `0x180004880`
- `0x180005ea0`
- `0x18000c574`

## string_xrefs

- `0x180005eb1`: `DoInfInstall: InfFile=%1\n`
- `0x180005f5d`: `DoInfInstall: %1 End hr=0x%2!x!\n`

## pseudocode

```c
__int64 __fastcall DoInfInstallW(struct _ADVPACKARGSW *a1)
{
  unsigned int v2; // edi

  AdvWriteToLog(L"DoInfInstall: InfFile=%1\r\n", *((_QWORD *)a1 + 2));
  if ( (unsigned int)SaveGlobalContext() )
  {
    hWnd = *(HWND *)a1;
    pszTitleString = (LPCWSTR)*((_QWORD *)a1 + 1);
    ctx = *((_WORD *)a1 + 20);
    word_1800257D2 = *((_WORD *)a1 + 22);
    dword_1800257FC = (*((_DWORD *)a1 + 11) >> 17) & 1;
    dword_1800257D4 = (*((_DWORD *)a1 + 11) >> 18) & 1;
    v2 = CoreInstall(
           *((const unsigned __int16 **)a1 + 2),
           *((const unsigned __int16 **)a1 + 4),
           *((unsigned __int16 **)a1 + 3),
           *((_DWORD *)a1 + 12),
           (*((_DWORD *)a1 + 11) >> 10) & 0x600 | ~(unsigned __int8)(*((_DWORD *)a1 + 11) >> 15) & 2u,
           0);
    RestoreGlobalContext();
  }
  else
  {
    v2 = -2147024882;
  }
  AdvWriteToLog(L"DoInfInstall: %1 End hr=0x%2!x!\r\n", *((_QWORD *)a1 + 2), v2);
  return v2;
}

```

## disassembly

```asm
0x180005ea0  mov     [rsp+arg_0], rbx
0x180005ea5  push    rdi
0x180005ea6  sub     rsp, 30h
0x180005eaa  mov     rdx, [rcx+10h]
0x180005eae  mov     rbx, rcx
0x180005eb1  lea     rcx, aDoinfinstallIn; "DoInfInstall: InfFile=%1\r\n"
0x180005eb8  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180005ebd  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x180005ec2  test    eax, eax
0x180005ec4  jnz     short loc_180005ED0
0x180005ec6  mov     edi, 8007000Eh
0x180005ecb  jmp     loc_180005F59
0x180005ed0  mov     rax, [rbx]
0x180005ed3  mov     cs:hWnd, rax
0x180005eda  mov     rax, [rbx+8]
0x180005ede  mov     cs:pszTitleString, rax
0x180005ee5  movzx   eax, word ptr [rbx+28h]
0x180005ee9  mov     cs:?ctx@@3UADVCONTEXTW@@A, ax; ADVCONTEXTW ctx
0x180005ef0  movzx   eax, word ptr [rbx+2Ch]
0x180005ef4  mov     cs:word_1800257D2, ax
0x180005efb  mov     eax, [rbx+2Ch]
0x180005efe  shr     eax, 11h
0x180005f01  and     eax, 1
0x180005f04  mov     [rsp+38h+var_10], 0; unsigned __int16 *
0x180005f0d  mov     cs:dword_1800257FC, eax
0x180005f13  mov     eax, [rbx+2Ch]
0x180005f16  shr     eax, 12h
0x180005f19  and     eax, 1
0x180005f1c  mov     cs:dword_1800257D4, eax
0x180005f22  mov     eax, [rbx+2Ch]
0x180005f25  mov     ecx, eax
0x180005f27  mov     r9d, [rbx+30h]; unsigned int
0x180005f2b  mov     r8, [rbx+18h]; unsigned __int16 *
0x180005f2f  mov     rdx, [rbx+20h]; unsigned __int16 *
0x180005f33  shr     ecx, 0Fh
0x180005f36  not     ecx
0x180005f38  shr     eax, 0Ah
0x180005f3b  and     ecx, 2
0x180005f3e  and     eax, 600h
0x180005f43  or      ecx, eax
0x180005f45  mov     [rsp+38h+var_18], ecx; ULONG
0x180005f49  mov     rcx, [rbx+10h]; unsigned __int16 *
0x180005f4d  call    ?CoreInstall@@YAJPEBG00KK0@Z; CoreInstall(ushort const *,ushort const *,ushort const *,ulong,ulong,ushort const *)
0x180005f52  mov     edi, eax
0x180005f54  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x180005f59  mov     rdx, [rbx+10h]
0x180005f5d  lea     rcx, aDoinfinstall1E; "DoInfInstall: %1 End hr=0x%2!x!\r\n"
0x180005f64  mov     r8d, edi
0x180005f67  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180005f6c  mov     rbx, [rsp+38h+arg_0]
0x180005f71  mov     eax, edi
0x180005f73  add     rsp, 30h
0x180005f77  pop     rdi
0x180005f78  retn
```
