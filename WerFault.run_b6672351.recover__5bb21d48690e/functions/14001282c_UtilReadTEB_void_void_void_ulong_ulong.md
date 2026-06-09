# UtilReadTEB(void *,void *,void *,ulong,ulong)

- ea: `0x14001282c`
- end: `0x14001298e`
- name: `?UtilReadTEB@@YAJPEAX00KK@Z`
- size: `354`
- prototype: `__int64 __usercall@<rax>(HANDLE hProcess@<rcx>, HANDLE ThreadHandle@<rdx>, void *lpBuffer@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400481cc`
- `0x140049fc0`

## callees

- `0x14001282c`
- `0x140014ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012924`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400128e6`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400128e6`
- `ntdll!NtQueryInformationThread` at `0x14001287e`
- `ntdll!NtQueryInformationThread` at `0x14001287e`

## pseudocode

```c
__int64 __fastcall UtilReadTEB(
        HANDLE hProcess,
        HANDLE ThreadHandle,
        void *lpBuffer,
        unsigned int a4,
        unsigned int nSize)
{
  __int64 v5; // rsi
  NTSTATUS InformationThread; // ebx
  signed int v9; // ebx
  signed int LastError; // eax
  _OWORD ThreadInformation[5]; // [rsp+30h] [rbp-58h] BYREF

  v5 = a4;
  memset(ThreadInformation, 0, 48);
  if ( ThreadHandle && lpBuffer )
  {
    InformationThread = NtQueryInformationThread(ThreadHandle, ThreadBasicInformation, ThreadInformation, 0x30u, 0);
    if ( InformationThread >= 0 )
    {
      if ( ReadProcessMemory(hProcess, (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + v5), lpBuffer, nSize, 0) )
      {
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
        }
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 >= 0 )
          return (unsigned int)-2147467259;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
      }
      return (unsigned int)(InformationThread | 0x10000000);
    }
    return (unsigned int)v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14001282c  push    rbx
0x14001282e  push    rbp
0x14001282f  push    rsi
0x140012830  push    rdi
0x140012831  sub     rsp, 68h
0x140012835  mov     esi, r9d
0x140012838  xorps   xmm0, xmm0
0x14001283b  mov     rdi, r8
0x14001283e  mov     rax, rdx
0x140012841  mov     rbp, rcx
0x140012844  movups  [rsp+88h+ThreadInformation], xmm0
0x140012849  movups  [rsp+88h+var_48], xmm0
0x14001284e  movups  [rsp+88h+var_38], xmm0
0x140012853  test    rdx, rdx
0x140012856  jz      loc_140012951
0x14001285c  test    r8, r8
0x14001285f  jz      loc_140012951
0x140012865  mov     r9d, 30h ; '0'; ThreadInformationLength
0x14001286b  mov     [rsp+88h+ReturnLength], 0; ReturnLength
0x140012874  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x140012879  xor     edx, edx; ThreadInformationClass
0x14001287b  mov     rcx, rax; ThreadHandle
0x14001287e  call    cs:__imp_NtQueryInformationThread
0x140012885  nop     dword ptr [rax+rax+00h]
0x14001288a  mov     ebx, eax
0x14001288c  test    eax, eax
0x14001288e  jns     short loc_1400128C7
0x140012890  mov     rcx, cs:WPP_GLOBAL_Control
0x140012897  lea     rax, WPP_GLOBAL_Control
0x14001289e  cmp     rcx, rax
0x1400128a1  jz      short loc_1400128BE
0x1400128a3  test    byte ptr [rcx+1Ch], 1
0x1400128a7  jz      short loc_1400128BE
0x1400128a9  mov     rcx, [rcx+10h]
0x1400128ad  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1400128b4  mov     edx, 37h ; '7'
0x1400128b9  call    WPP_SF_
0x1400128be  bts     ebx, 1Ch
0x1400128c2  jmp     loc_14001294D
0x1400128c7  mov     r9d, dword ptr [rsp+88h+nSize]; nSize
0x1400128cf  mov     rdx, rsi
0x1400128d2  add     rdx, qword ptr [rsp+88h+ThreadInformation+8]; lpBaseAddress
0x1400128d7  mov     r8, rdi; lpBuffer
0x1400128da  mov     rcx, rbp; hProcess
0x1400128dd  mov     [rsp+88h+ReturnLength], 0; lpNumberOfBytesRead
0x1400128e6  call    cs:__imp_ReadProcessMemory
0x1400128ed  nop     dword ptr [rax+rax+00h]
0x1400128f2  test    eax, eax
0x1400128f4  jnz     short loc_14001294B
0x1400128f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128fd  lea     rax, WPP_GLOBAL_Control
0x140012904  cmp     rcx, rax
0x140012907  jz      short loc_140012924
0x140012909  test    byte ptr [rcx+1Ch], 1
0x14001290d  jz      short loc_140012924
0x14001290f  mov     rcx, [rcx+10h]
0x140012913  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x14001291a  mov     edx, 38h ; '8'
0x14001291f  call    WPP_SF_
0x140012924  call    cs:__imp_GetLastError
0x14001292b  nop     dword ptr [rax+rax+00h]
0x140012930  mov     ebx, eax
0x140012932  test    eax, eax
0x140012934  jle     short loc_14001293F
0x140012936  movzx   ebx, ax
0x140012939  or      ebx, 80070000h
0x14001293f  test    ebx, ebx
0x140012941  mov     eax, 80004005h
0x140012946  cmovns  ebx, eax
0x140012949  jmp     short loc_14001294D
0x14001294b  xor     ebx, ebx
0x14001294d  mov     eax, ebx
0x14001294f  jmp     short loc_140012984
0x140012951  mov     rcx, cs:WPP_GLOBAL_Control
0x140012958  lea     rax, WPP_GLOBAL_Control
0x14001295f  cmp     rcx, rax
0x140012962  jz      short loc_14001297F
0x140012964  test    byte ptr [rcx+1Ch], 1
0x140012968  jz      short loc_14001297F
0x14001296a  mov     rcx, [rcx+10h]
0x14001296e  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140012975  mov     edx, 36h ; '6'
0x14001297a  call    WPP_SF_
0x14001297f  mov     eax, 80070057h
0x140012984  add     rsp, 68h
0x140012988  pop     rdi
0x140012989  pop     rsi
0x14001298a  pop     rbp
0x14001298b  pop     rbx
0x14001298c  retn
```
