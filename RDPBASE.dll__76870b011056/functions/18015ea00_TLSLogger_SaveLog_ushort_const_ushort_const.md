# TLSLogger::SaveLog(ushort const *,ushort const *)

- ea: `0x18015ea00`
- end: `0x18015eb68`
- name: `?SaveLog@TLSLogger@@UEAAXPEBG0@Z`
- size: `360`
- prototype: `void __fastcall(TLSLogger *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x180078c20`
- `0x18015e3c4`
- `0x18015e57c`
- `0x18015ea00`
- `0x18015eb70`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015eb47`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015eb47`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18015ea8a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18015ea8a`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015eabd`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18015eabd`

## pseudocode

```c
void __fastcall TLSLogger::SaveLog(TLSLogger *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned __int64 v6; // r8
  HANDLE FileW; // rax
  void *v8; // rsi
  int v9; // ecx
  int i; // eax
  int v11; // edi
  __int64 v12; // rax
  __int64 v13; // r8
  TLSLogger *v14; // rcx
  int v15; // edx
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // ecx
  WCHAR FileName[264]; // [rsp+40h] [rbp-238h] BYREF

  TLSLogger::DeleteOldFiles(this, a3);
  if ( (!*((_DWORD *)this + 141) || *((_DWORD *)this + 140))
    && TLSLogger::CreateFullPath(this, FileName, v6, a2, a3) >= 0 )
  {
    FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
    v8 = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      if ( *((_DWORD *)this + 7) )
      {
        v9 = *((_DWORD *)this + 9);
        for ( i = v9 + 1; ; i = v11 + 1 )
        {
          v11 = 0;
          if ( v9 != *((_DWORD *)this + 2) - 1 )
            v11 = i;
          if ( *(_DWORD *)((unsigned int)(v11 * *((_DWORD *)this + 8)) + *((_QWORD *)this + 2) + 4LL) )
            break;
          v9 = v11;
        }
        do
        {
          v12 = *((_QWORD *)this + 2);
          v13 = (unsigned int)(*((_DWORD *)this + 8) * v11);
          v14 = (TLSLogger *)*(unsigned int *)(v13 + v12 + 4);
          if ( (_DWORD)v14 )
            TLSLogger::SaveTLSRecord(
              v14,
              v8,
              *(_DWORD *)(v13 + v12),
              (unsigned __int8 *)(v13 + v12 + 8),
              *(_DWORD *)(v13 + v12 + 4));
          v15 = *((_DWORD *)this + 9);
          v16 = v11 + 1;
          v17 = v11;
          v11 = 0;
          v18 = *((_DWORD *)this + 2) - 1;
          if ( v17 != v18 )
            v11 = v16;
          v19 = 0;
          if ( v15 != v18 )
            v19 = v15 + 1;
        }
        while ( v11 != v19 );
      }
      else
      {
        WriteFile(FileW, "No records\r\n", 0xDu, 0, 0);
      }
      CloseHandle(v8);
    }
  }
}

```

## disassembly

```asm
0x18015ea00  push    rbx
0x18015ea02  push    rsi
0x18015ea03  push    rdi
0x18015ea04  sub     rsp, 260h
0x18015ea0b  mov     rax, cs:__security_cookie
0x18015ea12  xor     rax, rsp
0x18015ea15  mov     [rsp+278h+var_28], rax
0x18015ea1d  mov     rsi, rdx
0x18015ea20  mov     rdi, r8
0x18015ea23  mov     rdx, r8; unsigned __int16 *
0x18015ea26  mov     rbx, rcx
0x18015ea29  call    ?DeleteOldFiles@TLSLogger@@AEAAXPEBG@Z; TLSLogger::DeleteOldFiles(ushort const *)
0x18015ea2e  cmp     dword ptr [rbx+234h], 0
0x18015ea35  jz      short loc_18015EA44
0x18015ea37  cmp     dword ptr [rbx+230h], 0
0x18015ea3e  jz      loc_18015EB4D
0x18015ea44  mov     r9, rsi; unsigned __int16 *
0x18015ea47  mov     qword ptr [rsp+278h+dwCreationDisposition], rdi; unsigned __int16 *
0x18015ea4c  lea     rdx, [rsp+278h+FileName]; unsigned __int16 *
0x18015ea51  mov     rcx, rbx; this
0x18015ea54  call    ?CreateFullPath@TLSLogger@@AEAAJPEAG_KPEBG2@Z; TLSLogger::CreateFullPath(ushort *,unsigned __int64,ushort const *,ushort const *)
0x18015ea59  test    eax, eax
0x18015ea5b  js      loc_18015EB4D
0x18015ea61  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x18015ea6a  lea     rcx, [rsp+278h+FileName]; lpFileName
0x18015ea6f  mov     [rsp+278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18015ea77  xor     r9d, r9d; lpSecurityAttributes
0x18015ea7a  xor     r8d, r8d; dwShareMode
0x18015ea7d  mov     [rsp+278h+dwCreationDisposition], 2; dwCreationDisposition
0x18015ea85  mov     edx, 40000000h; dwDesiredAccess
0x18015ea8a  call    cs:__imp_CreateFileW
0x18015ea90  mov     rsi, rax
0x18015ea93  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18015ea97  jz      loc_18015EB4D
0x18015ea9d  cmp     dword ptr [rbx+1Ch], 0
0x18015eaa1  jnz     short loc_18015EAC5
0x18015eaa3  xor     r9d, r9d; lpNumberOfBytesWritten
0x18015eaa6  mov     qword ptr [rsp+278h+dwCreationDisposition], 0; lpOverlapped
0x18015eaaf  lea     rdx, aNoRecords; "No records\r\n"
0x18015eab6  mov     rcx, rax; hFile
0x18015eab9  lea     r8d, [r9+0Dh]; nNumberOfBytesToWrite
0x18015eabd  call    cs:__imp_WriteFile
0x18015eac3  jmp     short loc_18015EB44
0x18015eac5  mov     ecx, [rbx+24h]
0x18015eac8  mov     r8d, [rbx+8]
0x18015eacc  mov     rdx, [rbx+10h]
0x18015ead0  dec     r8d
0x18015ead3  lea     eax, [rcx+1]
0x18015ead6  jmp     short loc_18015EADD
0x18015ead8  mov     ecx, edi
0x18015eada  lea     eax, [rdi+1]
0x18015eadd  xor     edi, edi
0x18015eadf  cmp     ecx, r8d
0x18015eae2  cmovnz  edi, eax
0x18015eae5  mov     eax, [rbx+20h]
0x18015eae8  imul    eax, edi
0x18015eaeb  cmp     dword ptr [rax+rdx+4], 0
0x18015eaf0  jz      short loc_18015EAD8
0x18015eaf2  mov     rax, [rbx+10h]
0x18015eaf6  mov     r8d, edi
0x18015eaf9  imul    r8d, [rbx+20h]
0x18015eafe  mov     ecx, [r8+rax+4]; this
0x18015eb03  test    ecx, ecx
0x18015eb05  jz      short loc_18015EB1E
0x18015eb07  lea     r9, [rax+8]
0x18015eb0b  mov     [rsp+278h+dwCreationDisposition], ecx; unsigned int
0x18015eb0f  add     r9, r8; unsigned __int8 *
0x18015eb12  mov     rdx, rsi; void *
0x18015eb15  mov     r8d, [r8+rax]; unsigned int
0x18015eb19  call    ?SaveTLSRecord@TLSLogger@@AEAAXPEAXKPEAEK@Z; TLSLogger::SaveTLSRecord(void *,ulong,uchar *,ulong)
0x18015eb1e  mov     edx, [rbx+24h]
0x18015eb21  lea     eax, [rdi+1]
0x18015eb24  mov     r8d, [rbx+8]
0x18015eb28  mov     ecx, edi
0x18015eb2a  xor     edi, edi
0x18015eb2c  dec     r8d
0x18015eb2f  cmp     ecx, r8d
0x18015eb32  cmovnz  edi, eax
0x18015eb35  xor     ecx, ecx
0x18015eb37  cmp     edx, r8d
0x18015eb3a  lea     eax, [rdx+1]
0x18015eb3d  cmovnz  ecx, eax
0x18015eb40  cmp     edi, ecx
0x18015eb42  jnz     short loc_18015EAF2
0x18015eb44  mov     rcx, rsi; hObject
0x18015eb47  call    cs:__imp_CloseHandle
0x18015eb4d  mov     rcx, [rsp+278h+var_28]
0x18015eb55  xor     rcx, rsp; StackCookie
0x18015eb58  call    __security_check_cookie
0x18015eb5d  add     rsp, 260h
0x18015eb64  pop     rdi
0x18015eb65  pop     rsi
0x18015eb66  pop     rbx
0x18015eb67  retn
```
