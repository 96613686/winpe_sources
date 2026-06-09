# __std_fs_get_stats(x,x,x,x)

- ea: `0x40c77d`
- end: `0x40c96c`
- name: `___std_fs_get_stats@16`
- size: `495`
- prototype: `DWORD __userpurge@<eax>(int@<ebp>, const WCHAR *, _DWORD *, unsigned int, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x408ad2`
- `0x408d24`
- `0x40c67d`

## callees

- `0x40b3e3`
- `0x40c4a8`
- `0x40c77d`
- `0x40c96c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x40c829`
- `KERNEL32!GetLastError` at `0x40c8be`
- `KERNEL32!GetLastError` at `0x40c829`
- `KERNEL32!GetLastError` at `0x40c8be`
- `KERNEL32!GetFileAttributesExW` at `0x40c81f`
- `KERNEL32!GetFileAttributesExW` at `0x40c81f`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c8b4`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c8f2`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c91e`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c8b4`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c8f2`
- `KERNEL32!GetFileInformationByHandleEx` at `0x40c91e`

## pseudocode

```c
DWORD __userpurge __std_fs_get_stats@<eax>(int a1@<ebp>, const WCHAR *a2, _DWORD *a3, unsigned int a4, int a5)
{
  char v5; // al
  unsigned int v6; // ecx
  unsigned __int8 v8; // al
  int v9; // ecx
  bool v10; // zf
  int v11; // eax
  int v12; // ecx
  int v13; // eax
  HANDLE v14; // esi
  DWORD LastError; // edi
  unsigned int v16; // eax
  int v17; // ecx
  int v18; // ecx
  HANDLE v19; // [esp-68h] [ebp-74h] BYREF
  int v20; // [esp-64h] [ebp-70h] BYREF
  int v21; // [esp-60h] [ebp-6Ch]
  unsigned __int8 v22; // [esp-59h] [ebp-65h]
  _DWORD v23[11]; // [esp-58h] [ebp-64h] BYREF
  int v24; // [esp-2Ch] [ebp-38h] BYREF
  int v25; // [esp-20h] [ebp-2Ch] BYREF
  int v26; // [esp-18h] [ebp-24h]
  int v27; // [esp-14h] [ebp-20h]
  int v28; // [esp-10h] [ebp-1Ch]
  int v29; // [esp-Ch] [ebp-18h]
  int v30; // [esp+0h] [ebp-Ch]
  void *v31; // [esp+4h] [ebp-8h]
  void *retaddr; // [esp+Ch] [ebp+0h]
  unsigned int v33; // [esp+18h] [ebp+Ch]

  v30 = a1;
  v31 = retaddr;
  v5 = a4 & 1;
  v6 = a4 & 0xFFFFFFFE;
  v22 = a4 & 1;
  v33 = a4 & 0xFFFFFFFE;
  if ( v5 && (v6 & 4) != 0 )
    return 87;
  if ( (v6 & 2) == 0 || a5 == -1 )
  {
    v8 = v22;
  }
  else
  {
    v8 = v22;
    if ( (a5 & 0x400) == 0 || !v22 )
    {
      v6 &= ~2u;
      a3[4] = a5;
      v33 = v6;
    }
  }
  if ( v6 )
  {
    if ( (v6 & 0x2A) == 0 || a5 != -1 && (a5 & 0x400) != 0 && v8 )
    {
LABEL_21:
      v13 = __std_fs_open_handle((int)&v19, a2, 0x80u, ((v8 ^ 1) + 16) << 21);
      v14 = v19;
      v21 = v13;
      if ( v13 )
      {
        LastError = v13;
LABEL_37:
        __std_fs_close_handle(v14);
        return LastError;
      }
      v16 = v33;
      if ( v33 != 6 && (v33 & 0x22) != 0 )
      {
        if ( !GetFileInformationByHandleEx(v19, FileBasicInfo, v23, 0x28u) )
        {
LABEL_26:
          LastError = GetLastError();
          goto LABEL_37;
        }
        v17 = v23[5];
        a3[4] = v23[8];
        *a3 = v23[4];
        v16 = v33 & 0xFFFFFFDD;
        a3[1] = v17;
        v33 &= 0xFFFFFFDD;
      }
      if ( (v16 & 6) != 0 )
      {
        if ( !GetFileInformationByHandleEx(v14, FileAttributeTagInfo, &v20, 8u) )
          goto LABEL_26;
        a3[4] = v20;
        a3[5] = v21;
        v16 = v33 & 0xFFFFFFF9;
        v33 &= 0xFFFFFFF9;
      }
      if ( (v16 & 0x18) != 0 )
      {
        if ( !GetFileInformationByHandleEx(v14, FileStandardInfo, &v25, 0x18u) )
          goto LABEL_26;
        v18 = v27;
        a3[2] = v26;
        a3[6] = v28;
        a3[3] = v18;
        v16 = v33 & 0xFFFFFFE7;
      }
      if ( v16 )
        LastError = 50;
      else
        LastError = 0;
      goto LABEL_37;
    }
    if ( !GetFileAttributesExW(a2, GetFileExInfoStandard, &v24) )
      return GetLastError();
    if ( v22 && (v24 & 0x400) != 0 )
      goto LABEL_20;
    a3[4] = v24;
    v9 = v28;
    a3[2] = v29;
    v10 = (v33 & 0xFFFFFFD5) == 0;
    v33 &= 0xFFFFFFD5;
    v11 = v26;
    a3[3] = v9;
    v12 = v27;
    *a3 = v11;
    a3[1] = v12;
    if ( !v10 )
    {
LABEL_20:
      v8 = v22;
      goto LABEL_21;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x40c77d  push    ebx
0x40c77e  mov     ebx, esp
0x40c780  push    ecx
0x40c781  push    ecx
0x40c782  and     esp, 0FFFFFFF8h
0x40c785  add     esp, 4
0x40c788  push    ebp
0x40c789  mov     ebp, [ebx+4]
0x40c78c  mov     [esp+0Ch+var_8], ebp
0x40c790  mov     ebp, esp
0x40c792  sub     esp, 68h
0x40c795  mov     eax, ___security_cookie
0x40c79a  xor     eax, ebp
0x40c79c  mov     [ebp-4], eax
0x40c79f  mov     ecx, [ebx+10h]
0x40c7a2  mov     al, cl
0x40c7a4  push    esi
0x40c7a5  mov     esi, [ebx+8]
0x40c7a8  and     al, 1
0x40c7aa  and     ecx, 0FFFFFFFEh
0x40c7ad  mov     [ebp-59h], al
0x40c7b0  mov     [ebx+10h], ecx
0x40c7b3  push    edi
0x40c7b4  mov     edi, [ebx+0Ch]
0x40c7b7  test    al, al
0x40c7b9  jz      short loc_40C7CC
0x40c7bb  mov     eax, ecx
0x40c7bd  shr     eax, 2
0x40c7c0  test    al, 1
0x40c7c2  jz      short loc_40C7CC
0x40c7c4  push    57h ; 'W'
0x40c7c6  pop     eax
0x40c7c7  jmp     loc_40C957
0x40c7cc  mov     edx, [ebx+14h]
0x40c7cf  mov     eax, ecx
0x40c7d1  shr     eax, 1
0x40c7d3  test    al, 1
0x40c7d5  jz      short loc_40C7F7
0x40c7d7  cmp     edx, 0FFFFFFFFh
0x40c7da  jz      short loc_40C7F7
0x40c7dc  mov     eax, edx
0x40c7de  shr     eax, 0Ah
0x40c7e1  test    al, 1
0x40c7e3  mov     al, [ebp-59h]
0x40c7e6  jz      short loc_40C7EC
0x40c7e8  test    al, al
0x40c7ea  jnz     short loc_40C7FA
0x40c7ec  and     ecx, 0FFFFFFFDh
0x40c7ef  mov     [edi+10h], edx
0x40c7f2  mov     [ebx+10h], ecx
0x40c7f5  jmp     short loc_40C7FA
0x40c7f7  mov     al, [ebp-59h]
0x40c7fa  test    ecx, ecx
0x40c7fc  jz      loc_40C955
0x40c802  test    cl, 2Ah
0x40c805  jz      short loc_40C872
0x40c807  cmp     edx, 0FFFFFFFFh
0x40c80a  jz      short loc_40C818
0x40c80c  shr     edx, 0Ah
0x40c80f  test    dl, 1
0x40c812  jz      short loc_40C818
0x40c814  test    al, al
0x40c816  jnz     short loc_40C872
0x40c818  lea     eax, [ebp-2Ch]
0x40c81b  push    eax; lpFileInformation
0x40c81c  push    0; fInfoLevelId
0x40c81e  push    esi; lpFileName
0x40c81f  call    ds:GetFileAttributesExW
0x40c825  test    eax, eax
0x40c827  jnz     short loc_40C834
0x40c829  call    ds:GetLastError
0x40c82f  jmp     loc_40C957
0x40c834  cmp     byte ptr [ebp-59h], 0
0x40c838  mov     ecx, [ebp-2Ch]
0x40c83b  jz      short loc_40C846
0x40c83d  mov     eax, ecx
0x40c83f  shr     eax, 0Ah
0x40c842  test    al, 1
0x40c844  jnz     short loc_40C86F
0x40c846  xor     eax, eax
0x40c848  mov     [edi+10h], ecx
0x40c84b  add     eax, [ebp-0Ch]
0x40c84e  mov     ecx, [ebp-10h]
0x40c851  adc     ecx, 0
0x40c854  mov     [edi+8], eax
0x40c857  and     dword ptr [ebx+10h], 0FFFFFFD5h
0x40c85b  mov     eax, [ebp-18h]
0x40c85e  mov     [edi+0Ch], ecx
0x40c861  mov     ecx, [ebp-14h]
0x40c864  mov     [edi], eax
0x40c866  mov     [edi+4], ecx
0x40c869  jz      loc_40C955
0x40c86f  mov     al, [ebp-59h]
0x40c872  movzx   eax, al
0x40c875  xor     eax, 1
0x40c878  add     eax, 10h
0x40c87b  shl     eax, 15h
0x40c87e  push    eax; dwFlagsAndAttributes
0x40c87f  push    80h; dwDesiredAccess
0x40c884  push    esi; lpFileName
0x40c885  lea     eax, [ebp-68h]
0x40c888  push    eax; int
0x40c889  call    ___std_fs_open_handle@16
0x40c88e  mov     esi, [ebp-68h]
0x40c891  mov     [ebp-60h], eax
0x40c894  test    eax, eax
0x40c896  jz      short loc_40C89F
0x40c898  mov     edi, eax
0x40c89a  jmp     loc_40C94B
0x40c89f  mov     eax, [ebx+10h]
0x40c8a2  cmp     eax, 6
0x40c8a5  jz      short loc_40C8E5
0x40c8a7  test    al, 22h
0x40c8a9  jz      short loc_40C8E5
0x40c8ab  push    28h ; '('; dwBufferSize
0x40c8ad  lea     eax, [ebp-58h]
0x40c8b0  push    eax; lpFileInformation
0x40c8b1  push    0; FileInformationClass
0x40c8b3  push    esi; hFile
0x40c8b4  call    ds:GetFileInformationByHandleEx
0x40c8ba  test    eax, eax
0x40c8bc  jnz     short loc_40C8CB
0x40c8be  call    ds:GetLastError
0x40c8c4  mov     edi, eax
0x40c8c6  jmp     loc_40C94B
0x40c8cb  mov     eax, [ebp-38h]
0x40c8ce  mov     ecx, [ebp-44h]
0x40c8d1  mov     [edi+10h], eax
0x40c8d4  mov     eax, [ebp-48h]
0x40c8d7  mov     [edi], eax
0x40c8d9  mov     eax, [ebx+10h]
0x40c8dc  and     eax, 0FFFFFFDDh
0x40c8df  mov     [edi+4], ecx
0x40c8e2  mov     [ebx+10h], eax
0x40c8e5  test    al, 6
0x40c8e7  jz      short loc_40C911
0x40c8e9  push    8; dwBufferSize
0x40c8eb  lea     eax, [ebp-64h]
0x40c8ee  push    eax; lpFileInformation
0x40c8ef  push    9; FileInformationClass
0x40c8f1  push    esi; hFile
0x40c8f2  call    ds:GetFileInformationByHandleEx
0x40c8f8  test    eax, eax
0x40c8fa  jz      short loc_40C8BE
0x40c8fc  mov     eax, [ebp-64h]
0x40c8ff  mov     [edi+10h], eax
0x40c902  mov     eax, [ebp-60h]
0x40c905  mov     [edi+14h], eax
0x40c908  mov     eax, [ebx+10h]
0x40c90b  and     eax, 0FFFFFFF9h
0x40c90e  mov     [ebx+10h], eax
0x40c911  test    al, 18h
0x40c913  jz      short loc_40C940
0x40c915  push    18h; dwBufferSize
0x40c917  lea     eax, [ebp-20h]
0x40c91a  push    eax; lpFileInformation
0x40c91b  push    1; FileInformationClass
0x40c91d  push    esi; hFile
0x40c91e  call    ds:GetFileInformationByHandleEx
0x40c924  test    eax, eax
0x40c926  jz      short loc_40C8BE
0x40c928  mov     eax, [ebp-18h]
0x40c92b  mov     ecx, [ebp-14h]
0x40c92e  mov     [edi+8], eax
0x40c931  mov     eax, [ebp-10h]
0x40c934  mov     [edi+18h], eax
0x40c937  mov     eax, [ebx+10h]
0x40c93a  mov     [edi+0Ch], ecx
0x40c93d  and     eax, 0FFFFFFE7h
0x40c940  test    eax, eax
0x40c942  jnz     short loc_40C948
0x40c944  xor     edi, edi
0x40c946  jmp     short loc_40C94B
0x40c948  push    32h ; '2'
0x40c94a  pop     edi
0x40c94b  push    esi; hObject
0x40c94c  call    ___std_fs_close_handle@4
0x40c951  mov     eax, edi
0x40c953  jmp     short loc_40C957
0x40c955  xor     eax, eax
0x40c957  mov     ecx, [ebp-4]
0x40c95a  pop     edi
0x40c95b  xor     ecx, ebp; StackCookie
0x40c95d  pop     esi
0x40c95e  call    @__security_check_cookie@4
0x40c963  mov     esp, ebp
0x40c965  pop     ebp
0x40c966  mov     esp, ebx
0x40c968  pop     ebx
0x40c969  retn    10h
```
