# RunAllCommandLines

- ea: `0x1400100a4`
- end: `0x14001024f`
- name: `RunAllCommandLines`
- size: `427`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x1400100a4`
- `0x140010258`
- `0x14003ec14`
- `0x14004eb34`

## import_xrefs

- `KERNEL32!PowerClearRequest` at `0x1400101dc`
- `KERNEL32!PowerClearRequest` at `0x1400101dc`
- `KERNEL32!CloseHandle` at `0x14001022e`
- `KERNEL32!CloseHandle` at `0x14001022e`
- `KERNEL32!GetLastError` at `0x14001015c`
- `KERNEL32!GetLastError` at `0x140010170`
- `KERNEL32!GetLastError` at `0x140010200`
- `KERNEL32!GetLastError` at `0x14001015c`
- `KERNEL32!GetLastError` at `0x140010170`
- `KERNEL32!GetLastError` at `0x140010200`
- `KERNEL32!PowerCreateRequest` at `0x14001011e`
- `KERNEL32!PowerCreateRequest` at `0x14001011e`
- `KERNEL32!PowerSetRequest` at `0x140010135`
- `KERNEL32!PowerSetRequest` at `0x140010135`

## pseudocode

```c
__int64 __fastcall RunAllCommandLines(unsigned int **a1, mlib::XmlStream *a2)
{
  unsigned int v2; // ebp
  int v3; // r15d
  bool v4; // si
  char *v7; // rax
  char *v8; // rdi
  DWORD v9; // eax
  DWORD LastError; // eax
  unsigned int *i; // rbx
  unsigned int v12; // eax
  DWORD v13; // eax
  _REASON_CONTEXT Context; // [rsp+20h] [rbp-48h] BYREF
  int v16; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  v3 = 0;
  v4 = 0;
  memset(&Context, 0, sizeof(Context));
  if ( App::s_IsPrivateBld )
  {
    v16 = 0;
    if ( !(unsigned int)RegHelper::ReadDWORDValue(a1, L"PrivateError", &v16, 0) )
      v4 = v16 != 0;
  }
  Context.Version = 0;
  Context.Reason.Detailed.LocalizedReasonModule = (HMODULE)L"WinSAT Execution";
  Context.Flags = 1;
  v7 = (char *)PowerCreateRequest(&Context);
  v8 = v7;
  if ( v7 == (char *)-1LL )
  {
    LastError = GetLastError();
    Log_Text_F(
      (__int64)"base\\winsat\\exe\\main.cpp",
      3831,
      "ERROR: Failure creating power request. gle=0x%X",
      LastError);
  }
  else if ( PowerSetRequest(v7, PowerRequestExecutionRequired) )
  {
    v3 = 1;
    Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", 3826, "> Power 'execution' request successfully set.");
  }
  else
  {
    v9 = GetLastError();
    Log_Text_F(
      (__int64)"base\\winsat\\exe\\main.cpp",
      3828,
      "ERROR: Failure setting power 'execution' request. gle=0x%X",
      v9);
  }
  for ( i = *a1; i != a1[1]; i += 6 )
  {
    v12 = RunAnAssessment((StatusUpdate *)*i, (__int64)(i + 2), *((_BYTE *)i + 17), a2);
    if ( v12 )
    {
      if ( *((_BYTE *)i + 16) || v4 )
      {
        v2 = v12;
        break;
      }
      if ( v12 == 3 )
      {
        v2 = 3;
        break;
      }
    }
  }
  if ( v3 == 1 )
  {
    if ( PowerClearRequest(v8, PowerRequestExecutionRequired) )
    {
      Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", 3865, "> Power request 'execution' successfully cleared.");
    }
    else
    {
      v13 = GetLastError();
      Log_Text_F((__int64)"base\\winsat\\exe\\main.cpp", 3867, "ERROR: Failure clearing power request. gle=0x%X", v13);
    }
  }
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  return v2;
}

```

## disassembly

```asm
0x1400100a4  mov     rax, rsp
0x1400100a7  mov     [rax+10h], rbx
0x1400100ab  mov     [rax+18h], rbp
0x1400100af  push    rsi
0x1400100b0  push    rdi
0x1400100b1  push    r12
0x1400100b3  push    r14
0x1400100b5  push    r15
0x1400100b7  sub     rsp, 40h
0x1400100bb  xor     ebp, ebp
0x1400100bd  xorps   xmm0, xmm0
0x1400100c0  xor     r15d, r15d
0x1400100c3  xor     sil, sil
0x1400100c6  cmp     cs:?s_IsPrivateBld@App@@2_NA, sil; bool App::s_IsPrivateBld
0x1400100cd  mov     r12, rdx
0x1400100d0  mov     r14, rcx
0x1400100d3  lea     ebx, [rbp+1]
0x1400100d6  movups  xmmword ptr [rax-48h], xmm0
0x1400100da  movups  xmmword ptr [rax-38h], xmm0
0x1400100de  jz      short loc_140010105
0x1400100e0  xor     r9d, r9d
0x1400100e3  mov     [rax+8], ebp
0x1400100e6  lea     r8, [rax+8]
0x1400100ea  lea     rdx, aPrivateerror; "PrivateError"
0x1400100f1  call    ?ReadDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAKPEA_N@Z; RegHelper::ReadDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &,bool *)
0x1400100f6  test    eax, eax
0x1400100f8  jnz     short loc_140010105
0x1400100fa  cmp     [rsp+68h+arg_0], ebp
0x1400100fe  movzx   esi, sil
0x140010102  cmovnz  esi, ebx
0x140010105  lea     rax, aWinsatExecutio; "WinSAT Execution"
0x14001010c  mov     [rsp+68h+Context.Version], ebp
0x140010110  lea     rcx, [rsp+68h+Context]; Context
0x140010115  mov     qword ptr [rsp+68h+Context.Reason], rax
0x14001011a  mov     [rsp+68h+Context.Flags], ebx
0x14001011e  call    cs:__imp_PowerCreateRequest
0x140010124  mov     rdi, rax
0x140010127  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001012b  jz      short loc_140010170
0x14001012d  mov     edx, 3; RequestType
0x140010132  mov     rcx, rax; PowerRequest
0x140010135  call    cs:__imp_PowerSetRequest
0x14001013b  test    eax, eax
0x14001013d  jz      short loc_14001015C
0x14001013f  lea     r8, aPowerExecution; "> Power 'execution' request successfull"...
0x140010146  mov     edx, 0EF2h
0x14001014b  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x140010152  mov     r15d, ebx
0x140010155  call    Log_Text_F
0x14001015a  jmp     short loc_140010191
0x14001015c  call    cs:__imp_GetLastError
0x140010162  lea     r8, aErrorFailureSe; "ERROR: Failure setting power 'execution"...
0x140010169  mov     edx, 0EF4h
0x14001016e  jmp     short loc_140010182
0x140010170  call    cs:__imp_GetLastError
0x140010176  lea     r8, aErrorFailureCr; "ERROR: Failure creating power request. "...
0x14001017d  mov     edx, 0EF7h
0x140010182  mov     r9d, eax
0x140010185  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14001018c  call    Log_Text_F
0x140010191  mov     rbx, [r14]
0x140010194  cmp     rbx, [r14+8]
0x140010198  jz      short loc_1400101CF
0x14001019a  mov     r8b, [rbx+11h]
0x14001019e  lea     rdx, [rbx+8]
0x1400101a2  mov     ecx, [rbx]
0x1400101a4  mov     r9, r12
0x1400101a7  call    RunAnAssessment
0x1400101ac  test    eax, eax
0x1400101ae  jz      short loc_1400101C0
0x1400101b0  cmp     [rbx+10h], bpl
0x1400101b4  jnz     short loc_1400101CD
0x1400101b6  test    sil, sil
0x1400101b9  jnz     short loc_1400101CD
0x1400101bb  cmp     eax, 3
0x1400101be  jz      short loc_1400101C6
0x1400101c0  add     rbx, 18h
0x1400101c4  jmp     short loc_140010194
0x1400101c6  mov     ebp, 3
0x1400101cb  jmp     short loc_1400101CF
0x1400101cd  mov     ebp, eax
0x1400101cf  cmp     r15d, 1
0x1400101d3  jnz     short loc_140010221
0x1400101d5  lea     edx, [r15+2]; RequestType
0x1400101d9  mov     rcx, rdi; PowerRequest
0x1400101dc  call    cs:__imp_PowerClearRequest
0x1400101e2  test    eax, eax
0x1400101e4  jz      short loc_140010200
0x1400101e6  lea     r8, aPowerRequestEx; "> Power request 'execution' successfull"...
0x1400101ed  mov     edx, 0F19h
0x1400101f2  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x1400101f9  call    Log_Text_F
0x1400101fe  jmp     short loc_140010221
0x140010200  call    cs:__imp_GetLastError
0x140010206  lea     r8, aErrorFailureCl; "ERROR: Failure clearing power request. "...
0x14001020d  mov     edx, 0F1Bh
0x140010212  mov     r9d, eax
0x140010215  lea     rcx, aBaseWinsatExeM; "base\\winsat\\exe\\main.cpp"
0x14001021c  call    Log_Text_F
0x140010221  lea     rcx, [rdi-1]
0x140010225  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x140010229  ja      short loc_140010234
0x14001022b  mov     rcx, rdi; hObject
0x14001022e  call    cs:__imp_CloseHandle
0x140010234  lea     r11, [rsp+68h+var_28]
0x140010239  mov     eax, ebp
0x14001023b  mov     rbx, [r11+38h]
0x14001023f  mov     rbp, [r11+40h]
0x140010243  mov     rsp, r11
0x140010246  pop     r15
0x140010248  pop     r14
0x14001024a  pop     r12
0x14001024c  pop     rdi
0x14001024d  pop     rsi
0x14001024e  retn
```
