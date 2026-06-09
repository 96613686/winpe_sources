# BcpRegisterConfigChangeNotifyNoLogging

- ea: `0x18000997c`
- end: `0x180009b8f`
- name: `BcpRegisterConfigChangeNotifyNoLogging`
- size: `531`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009764`
- `0x180019500`

## callees

- `0x180002040`
- `0x18000283c`
- `0x180003860`
- `0x1800041d0`
- `0x180004200`
- `0x18000997c`
- `0x18000b094`
- `0x18001b7a9`
- `0x18001b7e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b44`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800099e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800099e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009b7e`

## pseudocode

```c
__int64 __fastcall BcpRegisterConfigChangeNotifyNoLogging(HANDLE *a1)
{
  unsigned __int8 *v2; // rdi
  NTSTATUS v3; // ebx
  HANDLE EventW; // rax
  char TrustedEnvironment; // al
  DWORD LastError; // esi
  size_t Size; // [rsp+48h] [rbp-E0h]
  size_t Sizea; // [rsp+48h] [rbp-E0h]
  unsigned int v10[4]; // [rsp+70h] [rbp-B8h] BYREF
  unsigned __int8 v11[128]; // [rsp+80h] [rbp-A8h] BYREF

  memset_0(v11, 0, sizeof(v11));
  v2 = v11;
  v10[0] = 0;
  if ( !a1 )
  {
    LastError = 87;
LABEL_15:
    v3 = WinErrorToNtStatus(LastError);
    goto LABEL_10;
  }
  *a1 = 0;
  v3 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *a1 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
LABEL_21:
    if ( *a1 )
    {
      CloseHandle(*a1);
      *a1 = 0;
    }
    if ( v3 < 0 )
      goto LABEL_10;
    goto LABEL_15;
  }
  TrustedEnvironment = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 1) != 0 )
  {
    LODWORD(Size) = 0;
    LastError = IoPack_Configuration_ParamBlock(0, 0, 0, 0, 0, 0, 0, 0, 0, Size, 0, *a1, v10, 0);
    if ( !LastError )
    {
      if ( v10[0] <= 0x80 || (v2 = (unsigned __int8 *)SafeAllocaAllocateFromHeap(v10[0])) != 0 )
      {
        LODWORD(Sizea) = 0;
        LastError = IoPack_Configuration_ParamBlock(0, 0, 0, 0, 0, 0, 0, 0, 0, Sizea, 0, *a1, 0, v2);
        if ( !LastError )
        {
          v3 = IoCallKernelDriver(66816, v2, v10[0], 0, 0);
          if ( v3 >= 0 )
          {
LABEL_10:
            if ( v2 && v2 != v11 )
              BCryptFree(v2);
            return (unsigned int)v3;
          }
        }
      }
      else
      {
        LastError = 8;
      }
    }
    goto LABEL_21;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000997c  mov     [rsp+arg_8], rbx
0x180009981  mov     [rsp+arg_10], rsi
0x180009986  push    rdi
0x180009987  push    r14
0x180009989  push    r15
0x18000998b  sub     rsp, 110h
0x180009992  mov     rax, cs:__security_cookie
0x180009999  xor     rax, rsp
0x18000999c  mov     [rsp+128h+var_28], rax
0x1800099a4  mov     r14, rcx
0x1800099a7  xor     edx, edx; Val
0x1800099a9  lea     rcx, [rsp+128h+var_A8]; void *
0x1800099b1  mov     r8d, 80h; Size
0x1800099b7  call    memset_0
0x1800099bc  xor     r15d, r15d
0x1800099bf  lea     rdi, [rsp+128h+var_A8]
0x1800099c7  mov     [rsp+128h+var_B8], r15d
0x1800099cc  test    r14, r14
0x1800099cf  jz      loc_180009B2E
0x1800099d5  xor     r9d, r9d; lpName
0x1800099d8  mov     [r14], r15
0x1800099db  xor     r8d, r8d; bInitialState
0x1800099de  xor     edx, edx; bManualReset
0x1800099e0  xor     ecx, ecx; lpEventAttributes
0x1800099e2  mov     ebx, r15d
0x1800099e5  call    cs:__imp_CreateEventW
0x1800099ec  nop     dword ptr [rax+rax+00h]
0x1800099f1  mov     [r14], rax
0x1800099f4  test    rax, rax
0x1800099f7  jz      loc_180009B44
0x1800099fd  mov     eax, cs:g_TrustedEnvironment
0x180009a03  test    eax, eax
0x180009a05  jz      loc_180009B54
0x180009a0b  test    al, 1
0x180009a0d  jz      loc_180009AEB
0x180009a13  mov     [rsp+128h+var_C0], r15; unsigned __int8 *
0x180009a18  lea     rax, [rsp+128h+var_B8]
0x180009a1d  mov     [rsp+128h+var_C8], rax; unsigned int *
0x180009a22  xor     r9d, r9d; unsigned __int16 *
0x180009a25  mov     rax, [r14]
0x180009a28  xor     r8d, r8d; unsigned int
0x180009a2b  mov     [rsp+128h+var_D0], rax; void *
0x180009a30  xor     edx, edx; unsigned __int16 *
0x180009a32  mov     [rsp+128h+var_D8], r15; unsigned __int8 *
0x180009a37  xor     ecx, ecx; unsigned int
0x180009a39  mov     dword ptr [rsp+128h+Size], r15d; Size
0x180009a3e  mov     [rsp+128h+var_E8], r15; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180009a43  mov     [rsp+128h+var_F0], r15; struct _CRYPT_CONTEXT_CONFIG *
0x180009a48  mov     [rsp+128h+var_F8], r15d; unsigned int
0x180009a4d  mov     [rsp+128h+var_100], r15; unsigned __int16 *
0x180009a52  mov     [rsp+128h+var_108], r15; Src
0x180009a57  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180009a5c  mov     esi, eax
0x180009a5e  test    eax, eax
0x180009a60  jnz     loc_180009B76
0x180009a66  cmp     [rsp+128h+var_B8], 80h
0x180009a6e  ja      loc_180009B5E
0x180009a74  mov     rax, [r14]
0x180009a77  xor     r9d, r9d; unsigned __int16 *
0x180009a7a  mov     [rsp+128h+var_C0], rdi; unsigned __int8 *
0x180009a7f  xor     r8d, r8d; unsigned int
0x180009a82  mov     [rsp+128h+var_C8], r15; unsigned int *
0x180009a87  xor     edx, edx; unsigned __int16 *
0x180009a89  mov     [rsp+128h+var_D0], rax; void *
0x180009a8e  xor     ecx, ecx; unsigned int
0x180009a90  mov     [rsp+128h+var_D8], r15; unsigned __int8 *
0x180009a95  mov     dword ptr [rsp+128h+Size], r15d; Size
0x180009a9a  mov     [rsp+128h+var_E8], r15; struct _CRYPT_CONTEXT_FUNCTION_CONFIG *
0x180009a9f  mov     [rsp+128h+var_F0], r15; struct _CRYPT_CONTEXT_CONFIG *
0x180009aa4  mov     [rsp+128h+var_F8], r15d; unsigned int
0x180009aa9  mov     [rsp+128h+var_100], r15; unsigned __int16 *
0x180009aae  mov     [rsp+128h+var_108], r15; Src
0x180009ab3  call    ?IoPack_Configuration_ParamBlock@@YAKKPEBGK000KPEAU_CRYPT_CONTEXT_CONFIG@@PEAU_CRYPT_CONTEXT_FUNCTION_CONFIG@@KPEAEPEAXPEAK3@Z; IoPack_Configuration_ParamBlock(ulong,ushort const *,ulong,ushort const *,ushort const *,ushort const *,ulong,_CRYPT_CONTEXT_CONFIG *,_CRYPT_CONTEXT_FUNCTION_CONFIG *,ulong,uchar *,void *,ulong *,uchar *)
0x180009ab8  mov     esi, eax
0x180009aba  test    eax, eax
0x180009abc  jnz     loc_180009B76
0x180009ac2  mov     r8d, [rsp+128h+var_B8]; unsigned int
0x180009ac7  xor     r9d, r9d; unsigned __int8 *
0x180009aca  mov     rdx, rdi; unsigned __int8 *
0x180009acd  mov     [rsp+128h+var_108], r15; unsigned int *
0x180009ad2  mov     ecx, 10500h; unsigned int
0x180009ad7  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x180009adc  mov     ebx, eax
0x180009ade  test    eax, eax
0x180009ae0  js      loc_180009B76
0x180009ae6  test    rdi, rdi
0x180009ae9  jnz     short loc_180009B17
0x180009aeb  mov     eax, ebx
0x180009aed  mov     rcx, [rsp+128h+var_28]
0x180009af5  xor     rcx, rsp; StackCookie
0x180009af8  call    __security_check_cookie
0x180009afd  lea     r11, [rsp+128h+var_18]
0x180009b05  mov     rbx, [r11+28h]
0x180009b09  mov     rsi, [r11+30h]
0x180009b0d  mov     rsp, r11
0x180009b10  pop     r15
0x180009b12  pop     r14
0x180009b14  pop     rdi
0x180009b15  retn
0x180009b17  lea     rax, [rsp+128h+var_A8]
0x180009b1f  cmp     rdi, rax
0x180009b22  jz      short loc_180009AEB
0x180009b24  mov     rcx, rdi
0x180009b27  call    BCryptFree
0x180009b2c  jmp     short loc_180009AEB
0x180009b2e  mov     esi, 57h ; 'W'
0x180009b33  mov     ecx, esi; Status
0x180009b35  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x180009b3a  mov     ebx, eax
0x180009b3c  jmp     short loc_180009AE6
0x180009b3e  test    ebx, ebx
0x180009b40  jns     short loc_180009B33
0x180009b42  jmp     short loc_180009AE6
0x180009b44  call    cs:__imp_GetLastError
0x180009b4b  nop     dword ptr [rax+rax+00h]
0x180009b50  mov     esi, eax
0x180009b52  jmp     short loc_180009B76
0x180009b54  call    GetTrustedEnvironment
0x180009b59  jmp     loc_180009A0B
0x180009b5e  mov     ecx, [rsp+128h+var_B8]
0x180009b62  call    SafeAllocaAllocateFromHeap
0x180009b67  mov     rdi, rax
0x180009b6a  test    rax, rax
0x180009b6d  jnz     loc_180009A74
0x180009b73  lea     esi, [rax+8]
0x180009b76  mov     rcx, [r14]; hObject
0x180009b79  test    rcx, rcx
0x180009b7c  jz      short loc_180009B3E
0x180009b7e  call    cs:__imp_CloseHandle
0x180009b85  nop     dword ptr [rax+rax+00h]
0x180009b8a  mov     [r14], r15
0x180009b8d  jmp     short loc_180009B3E
```
