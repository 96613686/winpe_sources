# BaseRegDeleteKeyExInternal

- ea: `0x180051e34`
- end: `0x180052198`
- name: `BaseRegDeleteKeyExInternal`
- size: `868`
- prototype: `__int64 __usercall@<rax>(HANDLE KeyHandle@<rcx>, PCUNICODE_STRING Source@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x180051cc0`

## callees

- `0x180051e34`
- `0x18005cb00`
- `0x18005cc40`
- `0x18005d6f0`
- `0x18005dd30`
- `0x18010b9f4`
- `0x18012d119`
- `0x18012ffa4`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180052020`
- `ntdll!RtlNtStatusToDosError` at `0x180052020`
- `ntdll!NtDeleteKey` at `0x180052008`
- `ntdll!NtDeleteKey` at `0x180052008`
- `ntdll!NtClose` at `0x180052013`
- `ntdll!NtClose` at `0x18005218d`
- `ntdll!NtClose` at `0x180052013`
- `ntdll!NtClose` at `0x18005218d`
- `ntdll!RtlFreeHeap` at `0x180051fd3`
- `ntdll!RtlFreeHeap` at `0x180052108`
- `ntdll!RtlFreeHeap` at `0x180051fd3`
- `ntdll!RtlFreeHeap` at `0x180052108`
- `ntdll!NtOpenKeyEx` at `0x180051fb3`
- `ntdll!NtOpenKeyEx` at `0x180051fb3`
- `ntdll!NtSetInformationKey` at `0x180052178`
- `ntdll!NtSetInformationKey` at `0x180052178`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteKey` at `0x180051ffb`
- `ext-ms-win-kernel32-registry-l1-1-0!TermsrvDeleteKey` at `0x180051ffb`

## pseudocode

```c
ULONG __fastcall BaseRegDeleteKeyExInternal(HANDLE KeyHandle, UNICODE_STRING *Source, __int16 a3, int a4, void *a5)
{
  HANDLE v7; // r15
  HANDLE v8; // rdi
  unsigned int Length; // ecx
  PWSTR Buffer; // rdx
  UNICODE_STRING v11; // xmm6
  unsigned int v12; // esi
  __int128 v13; // xmm0
  NTSTATUS KeySemantics; // ebx
  int v15; // esi
  int v17; // eax
  NTSTATUS v18; // eax
  __int64 v19; // [rsp+48h] [rbp-C0h] BYREF
  HANDLE KeySetInformation; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE KeyHandlea; // [rsp+58h] [rbp-B0h] BYREF
  HANDLE KeyHandle_8[2]; // [rsp+60h] [rbp-A8h] BYREF
  _OWORD v23[2]; // [rsp+70h] [rbp-98h]
  PVOID P; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v25[3]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v26[400]; // [rsp+C8h] [rbp-40h] BYREF

  KeyHandlea = KeyHandle;
  HIDWORD(KeyHandle_8[0]) = 0;
  HIDWORD(v23[0]) = 0;
  v7 = KeyHandle;
  KeySetInformation = 0;
  v8 = 0;
  if ( Source )
  {
    Length = Source->Length;
    if ( (unsigned __int16)Length >= 2u )
    {
      Buffer = Source->Buffer;
      if ( Buffer )
      {
        if ( (Length & 1) == 0 && !Buffer[((unsigned __int64)Length >> 1) - 1] && !a4 )
        {
          v11 = *Source;
          Source->Length = Length - 2;
          if ( ((unsigned __int8)v7 & 2) != 0
            || (g_RegKrnGlobalState & 2) != 0 && (v17 = ExtractClassKey(&KeyHandlea, Source, a5), v7 = KeyHandlea, v17) )
          {
            memset_0(v26, 0, 0x182u);
            *(HANDLE *)((char *)KeyHandle_8 + 4) = 0;
            *(_QWORD *)&v23[0] = v26;
            HIDWORD(KeyHandle_8[1]) = 386;
            LODWORD(KeyHandle_8[0]) = 0;
            KeySemantics = BaseRegGetKeySemantics(v7, Source);
            if ( KeySemantics >= 0 )
            {
              KeySemantics = BaseRegOpenClassKeyFromLocation(
                               (__int64)KeyHandle_8,
                               v7,
                               (__int64)Source,
                               a3 & 0x300 | 0x2000000u,
                               3,
                               0,
                               &KeySetInformation,
                               a5);
              if ( ((__int64)KeyHandle_8[0] & 0x20) != 0 )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)&v23[0]);
              v8 = KeySetInformation;
            }
            if ( KeySemantics < 0 )
              goto LABEL_21;
            goto LABEL_17;
          }
          v12 = a3 & 0x300 | 0x10000;
          LODWORD(KeyHandle_8[0]) = 48;
          KeyHandle_8[1] = (HANDLE)__PAIR64__(HIDWORD(KeyHandlea), (unsigned int)v7);
          DWORD2(v23[0]) = 64;
          *(_QWORD *)&v23[0] = Source;
          v23[1] = 0;
          if ( a5 )
          {
            v18 = Wow64NtOpenKey((unsigned int)&KeySetInformation, v12, (unsigned int)KeyHandle_8, 0, (__int64)a5);
            v8 = KeySetInformation;
            KeySemantics = v18;
          }
          else
          {
            v13 = *(_OWORD *)KeyHandle_8;
            KeyHandle_8[0] = 0;
            LOWORD(KeyHandle_8[1]) = 0;
            BYTE2(KeyHandle_8[1]) = 0;
            P = 0;
            v25[0] = v13;
            LODWORD(KeySetInformation) = 0;
            v25[1] = v23[0];
            KeyHandlea = 0;
            v25[2] = 0;
            LOBYTE(v19) = 0;
            KeySemantics = ConstructKernelKeyPath(
                             v12,
                             (unsigned int)v25,
                             (unsigned int)&KeySetInformation,
                             (unsigned int)KeyHandle_8,
                             (__int64)&v19,
                             (__int64)&P);
            if ( KeySemantics >= 0 )
            {
              v15 = NtOpenKeyEx(&KeyHandlea, v12, v25, 0);
              if ( P )
                RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
              if ( v15 >= 0 )
              {
                if ( (_BYTE)v19 )
                {
                  if ( (_DWORD)KeySetInformation )
                  {
                    LODWORD(KeySetInformation) = (unsigned __int16)KeySetInformation & 0xF01;
                    KeySemantics = NtSetInformationKey(KeyHandlea, KeySetHandleTagsInformation, &KeySetInformation, 4u);
                    if ( KeySemantics < 0 )
                    {
                      NtClose(KeyHandlea);
                      goto LABEL_17;
                    }
                  }
                }
                v8 = KeyHandlea;
              }
              KeySemantics = v15;
            }
          }
LABEL_17:
          if ( (unsigned __int8)IsTermsrvDeleteKeyPresent() )
            TermsrvDeleteKey(v8);
          if ( KeySemantics >= 0 )
          {
            KeySemantics = NtDeleteKey(v8);
            NtClose(v8);
          }
LABEL_21:
          *Source = v11;
          return RtlNtStatusToDosError(KeySemantics);
        }
      }
    }
  }
  return 87;
}

```

## disassembly

```asm
0x180051e34  mov     rax, rsp
0x180051e37  mov     [rax+20h], rbx
0x180051e3b  push    rbp
0x180051e3c  push    rsi
0x180051e3d  push    rdi
0x180051e3e  push    r12
0x180051e40  push    r13
0x180051e42  push    r14
0x180051e44  push    r15
0x180051e46  lea     rbp, [rax-1A8h]
0x180051e4d  sub     rsp, 270h
0x180051e54  movaps  xmmword ptr [rax-48h], xmm6
0x180051e58  mov     rax, cs:__security_cookie
0x180051e5f  xor     rax, rsp
0x180051e62  mov     [rbp+1A0h+var_50], rax
0x180051e69  mov     r12, [rbp+1A0h+arg_20]
0x180051e70  xor     r13d, r13d
0x180051e73  mov     [rsp+2A0h+KeyHandle], rcx
0x180051e78  mov     esi, r8d
0x180051e7b  mov     dword ptr [rsp+2A0h+KeyHandle+0Ch], r13d
0x180051e80  mov     r14, rdx
0x180051e83  mov     dword ptr [rsp+2A0h+var_230+4], r13d
0x180051e88  mov     r15, rcx
0x180051e8b  mov     [rsp+2A0h+KeySetInformation], r13
0x180051e90  mov     edi, r13d
0x180051e93  test    rdx, rdx
0x180051e96  jz      loc_180052120
0x180051e9c  movzx   ecx, word ptr [rdx]
0x180051e9f  mov     r8w, 2
0x180051ea4  cmp     cx, r8w
0x180051ea8  jb      loc_180052120
0x180051eae  mov     rdx, [rdx+8]
0x180051eb2  test    rdx, rdx
0x180051eb5  jz      loc_180052120
0x180051ebb  test    cl, 1
0x180051ebe  jnz     loc_180052120
0x180051ec4  mov     eax, ecx
0x180051ec6  shr     rax, 1
0x180051ec9  cmp     [rdx+rax*2-2], r13w
0x180051ecf  jnz     loc_180052120
0x180051ed5  test    r9d, r9d
0x180051ed8  jnz     loc_180052120
0x180051ede  movups  xmm6, xmmword ptr [r14]
0x180051ee2  sub     cx, r8w
0x180051ee6  mov     [r14], cx
0x180051eea  test    r8b, r15b
0x180051eed  jnz     loc_180052072
0x180051ef3  test    byte ptr cs:g_RegKrnGlobalState, r8b
0x180051efa  jnz     loc_180052055
0x180051f00  mov     eax, dword ptr [rsp+2A0h+KeyHandle+4]
0x180051f04  and     esi, 300h
0x180051f0a  bts     esi, 10h
0x180051f0e  mov     dword ptr [rsp+2A0h+KeyHandle+8], 30h ; '0'
0x180051f16  mov     dword ptr [rsp+2A0h+var_240], r15d
0x180051f1b  xorps   xmm2, xmm2
0x180051f1e  mov     dword ptr [rsp+2A0h+var_240+4], eax
0x180051f22  mov     dword ptr [rsp+2A0h+var_230], 40h ; '@'
0x180051f2a  mov     [rsp+2A0h+var_240+8], r14
0x180051f2f  movdqu  xmmword ptr [rsp+2A0h+var_230+8], xmm2
0x180051f35  test    r12, r12
0x180051f38  jnz     loc_18005212A
0x180051f3e  movups  xmm0, xmmword ptr [rsp+2A0h+KeyHandle+8]
0x180051f43  xor     eax, eax
0x180051f45  lea     r9, [rsp+2A0h+KeyHandle+8]
0x180051f4a  movups  xmm1, xmmword ptr [rsp+2A0h+var_240+8]
0x180051f4f  mov     [rsp+2A0h+KeyHandle+8], rax
0x180051f54  lea     r8, [rsp+2A0h+KeySetInformation]
0x180051f59  mov     word ptr [rsp+2A0h+var_240], ax
0x180051f5e  lea     rdx, [rbp+1A0h+var_210]
0x180051f62  mov     byte ptr [rsp+2A0h+var_240+2], al
0x180051f66  mov     ecx, esi
0x180051f68  lea     rax, [rbp+1A0h+P]
0x180051f6c  mov     [rbp+1A0h+P], r13
0x180051f70  mov     [rsp+2A0h+var_278], rax
0x180051f75  lea     rax, [rsp+2A0h+var_260]
0x180051f7a  mov     [rsp+2A0h+var_280], rax
0x180051f7f  movups  [rbp+1A0h+var_210], xmm0
0x180051f83  mov     dword ptr [rsp+2A0h+KeySetInformation], r13d
0x180051f88  movups  [rbp+1A0h+var_200], xmm1
0x180051f8c  mov     [rsp+2A0h+KeyHandle], r13
0x180051f91  movups  [rbp+1A0h+var_1F0], xmm2
0x180051f95  mov     byte ptr [rsp+2A0h+var_260], r13b
0x180051f9a  call    ConstructKernelKeyPath
0x180051f9f  mov     ebx, eax
0x180051fa1  test    eax, eax
0x180051fa3  js      short loc_180051FEF
0x180051fa5  xor     r9d, r9d
0x180051fa8  lea     r8, [rbp+1A0h+var_210]
0x180051fac  mov     edx, esi
0x180051fae  lea     rcx, [rsp+2A0h+KeyHandle]
0x180051fb3  call    cs:__imp_NtOpenKeyEx
0x180051fb9  mov     r8, [rbp+1A0h+P]; P
0x180051fbd  mov     esi, eax
0x180051fbf  test    r8, r8
0x180051fc2  jz      short loc_180051FD9
0x180051fc4  mov     rcx, gs:60h
0x180051fcd  xor     edx, edx; Flags
0x180051fcf  mov     rcx, [rcx+30h]; HeapHandle
0x180051fd3  call    cs:__imp_RtlFreeHeap
0x180051fd9  test    esi, esi
0x180051fdb  js      short loc_180051FED
0x180051fdd  cmp     byte ptr [rsp+2A0h+var_260], r13b
0x180051fe2  jnz     loc_18005214F
0x180051fe8  mov     rdi, [rsp+2A0h+KeyHandle]
0x180051fed  mov     ebx, esi
0x180051fef  call    IsTermsrvDeleteKeyPresent
0x180051ff4  test    al, al
0x180051ff6  jz      short loc_180052001
0x180051ff8  mov     rcx, rdi
0x180051ffb  call    cs:__imp_TermsrvDeleteKey
0x180052001  test    ebx, ebx
0x180052003  js      short loc_180052019
0x180052005  mov     rcx, rdi; KeyHandle
0x180052008  call    cs:__imp_NtDeleteKey
0x18005200e  mov     rcx, rdi; Handle
0x180052011  mov     ebx, eax
0x180052013  call    cs:__imp_NtClose
0x180052019  mov     ecx, ebx; Status
0x18005201b  movdqu  xmmword ptr [r14], xmm6
0x180052020  call    cs:__imp_RtlNtStatusToDosError
0x180052026  mov     rcx, [rbp+1A0h+var_50]
0x18005202d  xor     rcx, rsp; StackCookie
0x180052030  call    __security_check_cookie
0x180052035  lea     r11, [rsp+2A0h+var_30]
0x18005203d  mov     rbx, [r11+58h]
0x180052041  movaps  xmm6, xmmword ptr [r11-10h]
0x180052046  mov     rsp, r11
0x180052049  pop     r15
0x18005204b  pop     r14
0x18005204d  pop     r13
0x18005204f  pop     r12
0x180052051  pop     rdi
0x180052052  pop     rsi
0x180052053  pop     rbp
0x180052054  retn
0x180052055  mov     r8, r12
0x180052058  lea     rcx, [rsp+2A0h+KeyHandle]
0x18005205d  mov     rdx, r14
0x180052060  call    ExtractClassKey
0x180052065  mov     r15, [rsp+2A0h+KeyHandle]
0x18005206a  test    eax, eax
0x18005206c  jz      loc_180051F00
0x180052072  mov     ebx, 182h
0x180052077  lea     rcx, [rbp+1A0h+var_1E0]; void *
0x18005207b  mov     r8d, ebx; Size
0x18005207e  xor     edx, edx; Val
0x180052080  call    memset_0
0x180052085  lea     rax, [rbp+1A0h+var_1E0]
0x180052089  mov     [rsp+2A0h+KeyHandle+0Ch], r13
0x18005208e  lea     r8, [rsp+2A0h+KeyHandle+8]
0x180052093  mov     [rsp+2A0h+var_240+8], rax
0x180052098  mov     rdx, r14; Source
0x18005209b  mov     dword ptr [rsp+2A0h+var_240+4], ebx
0x18005209f  mov     rcx, r15; KeyHandle
0x1800520a2  mov     dword ptr [rsp+2A0h+KeyHandle+8], r13d
0x1800520a7  call    BaseRegGetKeySemantics
0x1800520ac  mov     ebx, eax
0x1800520ae  test    eax, eax
0x1800520b0  js      short loc_180052113
0x1800520b2  mov     qword ptr [rsp+2A0h+var_268], r12
0x1800520b7  lea     rax, [rsp+2A0h+KeySetInformation]
0x1800520bc  mov     [rsp+2A0h+var_270], rax
0x1800520c1  lea     rcx, [rsp+2A0h+KeyHandle+8]
0x1800520c6  and     esi, 300h
0x1800520cc  mov     dword ptr [rsp+2A0h+var_278], r13d
0x1800520d1  bts     esi, 19h
0x1800520d5  mov     dword ptr [rsp+2A0h+var_280], 3
0x1800520dd  mov     r9d, esi
0x1800520e0  mov     r8, r14
0x1800520e3  mov     rdx, r15
0x1800520e6  call    BaseRegOpenClassKeyFromLocation
0x1800520eb  test    byte ptr [rsp+2A0h+KeyHandle+8], 20h
0x1800520f0  mov     ebx, eax
0x1800520f2  jz      short loc_18005210E
0x1800520f4  mov     rcx, gs:60h
0x1800520fd  xor     edx, edx; Flags
0x1800520ff  mov     r8, [rsp+2A0h+var_240+8]; P
0x180052104  mov     rcx, [rcx+30h]; HeapHandle
0x180052108  call    cs:__imp_RtlFreeHeap
0x18005210e  mov     rdi, [rsp+2A0h+KeySetInformation]
0x180052113  test    ebx, ebx
0x180052115  jns     loc_180051FEF
0x18005211b  jmp     loc_180052019
0x180052120  mov     eax, 57h ; 'W'
0x180052125  jmp     loc_180052026
0x18005212a  xor     r9d, r9d
0x18005212d  mov     [rsp+2A0h+var_280], r12
0x180052132  lea     r8, [rsp+2A0h+KeyHandle+8]
0x180052137  mov     edx, esi
0x180052139  lea     rcx, [rsp+2A0h+KeySetInformation]
0x18005213e  call    Wow64NtOpenKey
0x180052143  mov     rdi, [rsp+2A0h+KeySetInformation]
0x180052148  mov     ebx, eax
0x18005214a  jmp     loc_180051FEF
0x18005214f  mov     eax, dword ptr [rsp+2A0h+KeySetInformation]
0x180052153  test    eax, eax
0x180052155  jz      loc_180051FE8
0x18005215b  mov     rcx, [rsp+2A0h+KeyHandle]; KeyHandle
0x180052160  lea     r8, [rsp+2A0h+KeySetInformation]; KeySetInformation
0x180052165  mov     r9d, 4; KeySetInformationLength
0x18005216b  and     eax, 0F01h
0x180052170  mov     dword ptr [rsp+2A0h+KeySetInformation], eax
0x180052174  lea     edx, [r9+1]; KeySetInformationClass
0x180052178  call    cs:__imp_NtSetInformationKey
0x18005217e  mov     ebx, eax
0x180052180  test    eax, eax
0x180052182  jns     loc_180051FE8
0x180052188  mov     rcx, [rsp+2A0h+KeyHandle]; Handle
0x18005218d  call    cs:__imp_NtClose
0x180052193  jmp     loc_180051FEF
```
