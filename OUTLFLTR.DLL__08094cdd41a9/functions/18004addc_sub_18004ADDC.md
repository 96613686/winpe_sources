# sub_18004ADDC

- ea: `0x18004addc`
- end: `0x18004aeff`
- name: `sub_18004ADDC`
- size: `291`
- prototype: `__int64 __fastcall(LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180035694`

## callees

- `0x18001a1cc`
- `0x18001dbd0`
- `0x18004addc`
- `0x18004b0e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004ae4f`
- `KERNEL32!GetLastError` at `0x18004ae4f`
- `KERNEL32!CreateIoCompletionPort` at `0x18004ae39`
- `KERNEL32!CreateIoCompletionPort` at `0x18004ae39`

## pseudocode

```c
__int64 __fastcall sub_18004ADDC(HANDLE *lpParameter)
{
  HANDLE IoCompletionPort; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  _BYTE *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int v9; // eax

  if ( !lpParameter[11] )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
    lpParameter[12] = IoCompletionPort;
    if ( IoCompletionPort )
    {
      v5 = 0;
    }
    else
    {
      LastError = GetLastError();
      v5 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v5 = LastError;
      v6 = off_1800A3660;
      if ( off_1800A3660 == (_UNKNOWN *)&off_1800A3660 || (*((_BYTE *)off_1800A3660 + 28) & 1) == 0 )
      {
LABEL_14:
        if ( (v5 & 0x80000000) == 0 )
        {
          v9 = sub_18004B0E0(lpParameter);
          v5 = v9;
          if ( v9 >= 0 )
            return 0;
          v6 = off_1800A3660;
          if ( off_1800A3660 == (_UNKNOWN *)&off_1800A3660 || (*((_BYTE *)off_1800A3660 + 28) & 1) == 0 )
            return v5;
          v7 = 12;
          v8 = (unsigned int)v9;
        }
        else
        {
          if ( v6 == (_BYTE *)&off_1800A3660 || (v6[28] & 1) == 0 )
            return v5;
          v7 = 11;
          v8 = v5;
        }
        sub_18001A1CC(*((_QWORD *)v6 + 2), v7, &stru_1800040F8, v8);
        return v5;
      }
      sub_18001A1CC(*((_QWORD *)off_1800A3660 + 2), 15, &stru_1800040F8, v5);
    }
    v6 = off_1800A3660;
    goto LABEL_14;
  }
  if ( off_1800A3660 != (_UNKNOWN *)&off_1800A3660 && (*((_BYTE *)off_1800A3660 + 28) & 2) != 0 )
    sub_18001DBD0(*((_QWORD *)off_1800A3660 + 2), 10, &stru_1800040F8);
  return 2147943647LL;
}

```

## disassembly

```asm
0x18004addc  mov     [rsp+arg_0], rbx
0x18004ade1  mov     [rsp+arg_8], rsi
0x18004ade6  push    rdi
0x18004ade7  sub     rsp, 20h
0x18004adeb  cmp     qword ptr [rcx+58h], 0
0x18004adf0  mov     rsi, rcx
0x18004adf3  jz      short loc_18004AE2D
0x18004adf5  mov     rcx, cs:off_1800A3660
0x18004adfc  lea     rdi, off_1800A3660
0x18004ae03  cmp     rcx, rdi
0x18004ae06  jz      short loc_18004AE23
0x18004ae08  test    byte ptr [rcx+1Ch], 2
0x18004ae0c  jz      short loc_18004AE23
0x18004ae0e  mov     rcx, [rcx+10h]
0x18004ae12  lea     r8, stru_1800040F8
0x18004ae19  mov     edx, 0Ah
0x18004ae1e  call    sub_18001DBD0
0x18004ae23  mov     eax, 800704DFh
0x18004ae28  jmp     loc_18004AEEF
0x18004ae2d  xor     r9d, r9d; NumberOfConcurrentThreads
0x18004ae30  xor     r8d, r8d; CompletionKey
0x18004ae33  xor     edx, edx; ExistingCompletionPort
0x18004ae35  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18004ae39  call    cs:CreateIoCompletionPort
0x18004ae3f  lea     rdi, off_1800A3660
0x18004ae46  mov     [rsi+60h], rax
0x18004ae4a  test    rax, rax
0x18004ae4d  jnz     short loc_18004AE8F
0x18004ae4f  call    cs:GetLastError
0x18004ae55  movzx   ebx, ax
0x18004ae58  or      ebx, 80070000h
0x18004ae5e  test    eax, eax
0x18004ae60  cmovle  ebx, eax
0x18004ae63  mov     rcx, cs:off_1800A3660
0x18004ae6a  cmp     rcx, rdi
0x18004ae6d  jz      short loc_18004AE98
0x18004ae6f  test    byte ptr [rcx+1Ch], 1
0x18004ae73  jz      short loc_18004AE98
0x18004ae75  mov     rcx, [rcx+10h]
0x18004ae79  lea     r8, stru_1800040F8
0x18004ae80  mov     edx, 0Fh
0x18004ae85  mov     r9d, ebx
0x18004ae88  call    sub_18001A1CC
0x18004ae8d  jmp     short loc_18004AE91
0x18004ae8f  xor     ebx, ebx
0x18004ae91  mov     rcx, cs:off_1800A3660
0x18004ae98  test    ebx, ebx
0x18004ae9a  jns     short loc_18004AEC3
0x18004ae9c  cmp     rcx, rdi
0x18004ae9f  jz      short loc_18004AEBF
0x18004aea1  test    byte ptr [rcx+1Ch], 1
0x18004aea5  jz      short loc_18004AEBF
0x18004aea7  mov     edx, 0Bh
0x18004aeac  mov     r9d, ebx
0x18004aeaf  mov     rcx, [rcx+10h]
0x18004aeb3  lea     r8, stru_1800040F8
0x18004aeba  call    sub_18001A1CC
0x18004aebf  mov     eax, ebx
0x18004aec1  jmp     short loc_18004AEEF
0x18004aec3  mov     rcx, rsi; lpParameter
0x18004aec6  call    sub_18004B0E0
0x18004aecb  mov     ebx, eax
0x18004aecd  test    eax, eax
0x18004aecf  jns     short loc_18004AEED
0x18004aed1  mov     rcx, cs:off_1800A3660
0x18004aed8  cmp     rcx, rdi
0x18004aedb  jz      short loc_18004AEBF
0x18004aedd  test    byte ptr [rcx+1Ch], 1
0x18004aee1  jz      short loc_18004AEBF
0x18004aee3  mov     edx, 0Ch
0x18004aee8  mov     r9d, eax
0x18004aeeb  jmp     short loc_18004AEAF
0x18004aeed  xor     eax, eax
0x18004aeef  mov     rbx, [rsp+28h+arg_0]
0x18004aef4  mov     rsi, [rsp+28h+arg_8]
0x18004aef9  add     rsp, 20h
0x18004aefd  pop     rdi
0x18004aefe  retn
```
