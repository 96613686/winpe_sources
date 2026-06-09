# BthServLoadBackgroundBrokerModule(void)

- ea: `0x18000c798`
- end: `0x18000c9d0`
- name: `?BthServLoadBackgroundBrokerModule@@YAXXZ`
- size: `568`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dc40`

## callees

- `0x18000c798`
- `0x1800110fc`
- `0x180011194`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c825`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c825`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c845`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c8c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c845`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c8c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c950`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c886`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c909`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c950`

## string_xrefs

- `0x18000c818`: `Windows.Internal.Devices.Bluetooth.dll`
- `0x18000c83b`: `BthEvtBrCreateBroker`
- `0x18000c8bd`: `BthEvtBrDeleteBroker`

## pseudocode

```c
void BthServLoadBackgroundBrokerModule(void)
{
  _BYTE *v0; // rcx
  char v1; // bl
  bool v2; // dl
  HMODULE Library; // rax
  bool v4; // di
  bool v5; // si
  int v6; // r8d
  int v7; // edx
  bool v8; // di
  bool v9; // si
  int v10; // edx
  int v11; // r8d
  int v12; // [rsp+20h] [rbp-68h]
  int v13; // [rsp+28h] [rbp-60h]
  __int16 v14; // [rsp+30h] [rbp-58h]

  v0 = WPP_GLOBAL_Control;
  v1 = 1;
  v2 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v0 = WPP_GLOBAL_Control;
  }
  if ( !hModule )
  {
    Library = LoadLibraryExW(L"Windows.Internal.Devices.Bluetooth.dll", 0, 0x800u);
    hModule = Library;
    if ( Library )
    {
      qword_180044A70 = (__int64)GetProcAddress(Library, "BthEvtBrCreateBroker");
      if ( !qword_180044A70 )
      {
        v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        v5 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          GetLastError();
          LOBYTE(v6) = v5;
          LOBYTE(v7) = v4;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v7,
            v6,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v12,
            v13,
            58,
            (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
        }
      }
      qword_180044A78 = (__int64)GetProcAddress(hModule, "BthEvtBrDeleteBroker");
      if ( qword_180044A78 )
        goto LABEL_34;
      v0 = WPP_GLOBAL_Control;
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        GetLastError();
        v14 = 59;
LABEL_33:
        LOBYTE(v11) = v9;
        LOBYTE(v10) = v8;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v10,
          v11,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v12,
          v13,
          v14,
          (__int64)WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids);
LABEL_34:
        v0 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v0 = WPP_GLOBAL_Control;
      v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
      v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        GetLastError();
        v14 = 60;
        goto LABEL_33;
      }
    }
  }
  if ( v0 == (_BYTE *)&WPP_GLOBAL_Control || v0[25] < 5u )
    v1 = 0;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v0 + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v0 + 5));
}

```

## disassembly

```asm
0x18000c798  push    rbx
0x18000c79a  push    rbp
0x18000c79b  push    rsi
0x18000c79c  push    rdi
0x18000c79d  push    r14
0x18000c79f  push    r15
0x18000c7a1  sub     rsp, 58h
0x18000c7a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c7ac  lea     rbp, WPP_GLOBAL_Control
0x18000c7b3  mov     bl, 1
0x18000c7b5  cmp     rcx, rbp
0x18000c7b8  jz      short loc_18000C7C4
0x18000c7ba  cmp     byte ptr [rcx+19h], 5
0x18000c7be  jb      short loc_18000C7C4
0x18000c7c0  mov     dl, bl
0x18000c7c2  jmp     short loc_18000C7C6
0x18000c7c4  xor     dl, dl
0x18000c7c6  lea     r14, WPP_RECORDER_INITIALIZED
0x18000c7cd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c7d4  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000c7db  setnz   r8b
0x18000c7df  test    dl, dl
0x18000c7e1  jnz     short loc_18000C7E8
0x18000c7e3  test    r8b, r8b
0x18000c7e6  jz      short loc_18000C808
0x18000c7e8  mov     r9, [rcx+28h]
0x18000c7ec  mov     rcx, [rcx+10h]
0x18000c7f0  mov     [rsp+88h+var_50], r15
0x18000c7f5  mov     [rsp+88h+var_58], 39h ; '9'
0x18000c7fc  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c801  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c808  cmp     cs:hModule, 0
0x18000c810  jnz     loc_18000C987
0x18000c816  xor     edx, edx; hFile
0x18000c818  lea     rcx, LibFileName; "Windows.Internal.Devices.Bluetooth.dll"
0x18000c81f  mov     r8d, 800h; dwFlags
0x18000c825  call    cs:__imp_LoadLibraryExW
0x18000c82b  mov     cs:hModule, rax
0x18000c832  test    rax, rax
0x18000c835  jz      loc_18000C921
0x18000c83b  lea     rdx, aBthevtbrcreate; "BthEvtBrCreateBroker"
0x18000c842  mov     rcx, rax; hModule
0x18000c845  call    cs:__imp_GetProcAddress
0x18000c84b  mov     cs:qword_180044A70, rax
0x18000c852  test    rax, rax
0x18000c855  jnz     short loc_18000C8B6
0x18000c857  mov     rax, cs:WPP_GLOBAL_Control
0x18000c85e  cmp     rax, rbp
0x18000c861  jz      short loc_18000C86E
0x18000c863  cmp     byte ptr [rax+19h], 3
0x18000c867  jb      short loc_18000C86E
0x18000c869  mov     dil, bl
0x18000c86c  jmp     short loc_18000C871
0x18000c86e  xor     dil, dil
0x18000c871  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c878  setnz   sil
0x18000c87c  test    dil, dil
0x18000c87f  jnz     short loc_18000C886
0x18000c881  test    sil, sil
0x18000c884  jz      short loc_18000C8B6
0x18000c886  call    cs:__imp_GetLastError
0x18000c88c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c893  mov     r8b, sil
0x18000c896  mov     [rsp+88h+var_40], eax
0x18000c89a  mov     dl, dil
0x18000c89d  mov     [rsp+88h+var_50], r15
0x18000c8a2  mov     [rsp+88h+var_58], 3Ah ; ':'
0x18000c8a9  mov     r9, [rcx+28h]
0x18000c8ad  mov     rcx, [rcx+10h]
0x18000c8b1  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000c8b6  mov     rcx, cs:hModule; hModule
0x18000c8bd  lea     rdx, aBthevtbrdelete; "BthEvtBrDeleteBroker"
0x18000c8c4  call    cs:__imp_GetProcAddress
0x18000c8ca  mov     cs:qword_180044A78, rax
0x18000c8d1  test    rax, rax
0x18000c8d4  jnz     loc_18000C980
0x18000c8da  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c8e1  cmp     rcx, rbp
0x18000c8e4  jz      short loc_18000C8F1
0x18000c8e6  cmp     byte ptr [rcx+19h], 3
0x18000c8ea  jb      short loc_18000C8F1
0x18000c8ec  mov     dil, bl
0x18000c8ef  jmp     short loc_18000C8F4
0x18000c8f1  xor     dil, dil
0x18000c8f4  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c8fb  setnz   sil
0x18000c8ff  test    dil, dil
0x18000c902  jnz     short loc_18000C909
0x18000c904  test    sil, sil
0x18000c907  jz      short loc_18000C987
0x18000c909  call    cs:__imp_GetLastError
0x18000c90f  mov     [rsp+88h+var_40], eax
0x18000c913  mov     [rsp+88h+var_50], r15
0x18000c918  mov     [rsp+88h+var_58], 3Bh ; ';'
0x18000c91f  jmp     short loc_18000C966
0x18000c921  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c928  cmp     rcx, rbp
0x18000c92b  jz      short loc_18000C938
0x18000c92d  cmp     byte ptr [rcx+19h], 3
0x18000c931  jb      short loc_18000C938
0x18000c933  mov     dil, bl
0x18000c936  jmp     short loc_18000C93B
0x18000c938  xor     dil, dil
0x18000c93b  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c942  setnz   sil
0x18000c946  test    dil, dil
0x18000c949  jnz     short loc_18000C950
0x18000c94b  test    sil, sil
0x18000c94e  jz      short loc_18000C987
0x18000c950  call    cs:__imp_GetLastError
0x18000c956  mov     [rsp+88h+var_40], eax
0x18000c95a  mov     [rsp+88h+var_50], r15
0x18000c95f  mov     [rsp+88h+var_58], 3Ch ; '<'
0x18000c966  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c96d  mov     r8b, sil
0x18000c970  mov     dl, dil
0x18000c973  mov     r9, [rcx+28h]
0x18000c977  mov     rcx, [rcx+10h]
0x18000c97b  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18000c980  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c987  cmp     rcx, rbp
0x18000c98a  jz      short loc_18000C992
0x18000c98c  cmp     byte ptr [rcx+19h], 5
0x18000c990  jnb     short loc_18000C994
0x18000c992  xor     bl, bl
0x18000c994  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000c99b  setnz   r8b
0x18000c99f  test    bl, bl
0x18000c9a1  jnz     short loc_18000C9A8
0x18000c9a3  test    r8b, r8b
0x18000c9a6  jz      short loc_18000C9C3
0x18000c9a8  mov     r9, [rcx+28h]
0x18000c9ac  mov     dl, bl
0x18000c9ae  mov     rcx, [rcx+10h]
0x18000c9b2  mov     [rsp+88h+var_50], r15
0x18000c9b7  mov     [rsp+88h+var_58], 3Dh ; '='
0x18000c9be  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000c9c3  add     rsp, 58h
0x18000c9c7  pop     r15
0x18000c9c9  pop     r14
0x18000c9cb  pop     rdi
0x18000c9cc  pop     rsi
0x18000c9cd  pop     rbp
0x18000c9ce  pop     rbx
0x18000c9cf  retn
```
