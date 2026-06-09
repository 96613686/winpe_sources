# Persistence_PowerResumed(void)

- ea: `0x18002fd30`
- end: `0x18002fec3`
- name: `?Persistence_PowerResumed@@YAXXZ`
- size: `403`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180045e60`

## callees

- `0x18001ff7c`
- `0x18002fd30`
- `0x180030840`
- `0x18003e920`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fe9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002fd5e`
- `ntdll!EtwEventWriteTransfer` at `0x18002fe80`
- `ntdll!EtwEventWriteTransfer` at `0x18002fe80`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void Persistence_PowerResumed(void)
{
  _QWORD *v0; // rbx
  __int64 v1; // rdi
  __int64 v2; // r10
  const WCHAR *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  _DWORD v6[2]; // [rsp+30h] [rbp-A8h] BYREF
  _DWORD v7[2]; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v8; // [rsp+40h] [rbp-98h]
  struct _RTL_CRITICAL_SECTION *v9; // [rsp+48h] [rbp-90h]
  unsigned __int16 *v10; // [rsp+50h] [rbp-88h]
  int v11; // [rsp+58h] [rbp-80h]
  int v12; // [rsp+5Ch] [rbp-7Ch]
  char *v13; // [rsp+60h] [rbp-78h]
  int v14; // [rsp+68h] [rbp-70h]
  int v15; // [rsp+6Ch] [rbp-6Ch]
  const WCHAR *v16; // [rsp+70h] [rbp-68h]
  int v17; // [rsp+78h] [rbp-60h]
  int v18; // [rsp+7Ch] [rbp-5Ch]
  _DWORD *v19; // [rsp+80h] [rbp-58h]
  __int64 v20; // [rsp+88h] [rbp-50h]

  EnterCriticalSection(&g_PersistedControlListLock);
  v9 = &g_PersistedControlListLock;
  v0 = g_PersistedControlList;
  while ( v0 )
  {
    v1 = v0[2];
    v0 = (_QWORD *)*v0;
    v2 = *((_QWORD *)AudioEndpointBuilderTelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v2 > 4u )
    {
      v6[0] = *(_DWORD *)(v1 + 64);
      v3 = *(const WCHAR **)(v1 + 72);
      v19 = v6;
      v20 = 4;
      if ( v3 )
      {
        v4 = -1;
        do
          ++v4;
        while ( v3[v4] );
        v5 = 2 * v4 + 2;
      }
      else
      {
        v3 = &LocaleName;
        v5 = 2;
      }
      v16 = v3;
      v17 = v5;
      v18 = 0;
      v7[0] = 184549376;
      v7[1] = 4;
      v8 = 0;
      v10 = *(unsigned __int16 **)(v2 + 8);
      v11 = *v10;
      v12 = 2;
      v13 = byte_1800778ED;
      v14 = 81;
      v15 = 1;
      v6[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(*(_QWORD *)(v2 + 32), v7, 0, 0);
    }
    CPersistedControl::RestorePersistedState((CPersistedControl *)v1, 0, 0);
  }
  LeaveCriticalSection(&g_PersistedControlListLock);
}

```

## disassembly

```asm
0x18002fd30  push    rbx
0x18002fd32  push    rbp
0x18002fd33  push    rsi
0x18002fd34  push    rdi
0x18002fd35  push    r12
0x18002fd37  push    r14
0x18002fd39  push    r15
0x18002fd3b  sub     rsp, 0A0h
0x18002fd42  mov     rax, cs:__security_cookie
0x18002fd49  xor     rax, rsp
0x18002fd4c  mov     [rsp+0D8h+var_48], rax
0x18002fd54  lea     rbp, ?g_PersistedControlListLock@@3Vcritical_section@wil@@A; wil::critical_section g_PersistedControlListLock
0x18002fd5b  mov     rcx, rbp; lpCriticalSection
0x18002fd5e  call    cs:__imp_EnterCriticalSection
0x18002fd64  mov     [rsp+0D8h+var_90], rbp
0x18002fd69  mov     rbx, cs:?g_PersistedControlList@@3V?$TList@VCPersistedControl@@@@A; TList<CPersistedControl> g_PersistedControlList
0x18002fd70  xor     esi, esi
0x18002fd72  lea     r14, byte_1800778ED
0x18002fd79  lea     r15, _TraceLoggingMetadataEnd
0x18002fd80  lea     r12, _TraceLoggingMetadata
0x18002fd87  test    rbx, rbx
0x18002fd8a  jz      loc_18002FE98
0x18002fd90  mov     rdi, [rbx+10h]
0x18002fd94  mov     rbx, [rbx]
0x18002fd97  call    ?Instance@AudioEndpointBuilderTelemetryProvider@@KAPEAV1@XZ; AudioEndpointBuilderTelemetryProvider::Instance(void)
0x18002fd9c  mov     r10, [rax+8]
0x18002fda0  mov     eax, [r10]
0x18002fda3  cmp     eax, 4
0x18002fda6  jbe     loc_18002FE86
0x18002fdac  mov     eax, [rdi+40h]
0x18002fdaf  mov     [rsp+0D8h+var_A8], eax
0x18002fdb3  mov     rcx, [rdi+48h]
0x18002fdb7  lea     rax, [rsp+0D8h+var_A8]
0x18002fdbc  mov     [rsp+0D8h+var_58], rax
0x18002fdc4  mov     [rsp+0D8h+var_50], 4
0x18002fdd0  test    rcx, rcx
0x18002fdd3  jz      short loc_18002FDF3
0x18002fdd5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002fddc  nop     dword ptr [rax+00h]
0x18002fde0  lea     rax, [rax+1]
0x18002fde4  cmp     [rcx+rax*2], si
0x18002fde8  jnz     short loc_18002FDE0
0x18002fdea  lea     eax, ds:2[rax*2]
0x18002fdf1  jmp     short loc_18002FDFF
0x18002fdf3  lea     rcx, LocaleName
0x18002fdfa  mov     eax, 2
0x18002fdff  mov     [rsp+0D8h+var_68], rcx
0x18002fe04  mov     [rsp+0D8h+var_60], eax
0x18002fe08  mov     [rsp+0D8h+var_5C], esi
0x18002fe0c  mov     [rsp+0D8h+var_A0], 0B000000h
0x18002fe14  movzx   eax, cs:word_1800778E3
0x18002fe1b  mov     [rsp+0D8h+var_9C], eax
0x18002fe1f  mov     [rsp+0D8h+var_98], rsi
0x18002fe24  mov     rax, [r10+8]
0x18002fe28  mov     [rsp+0D8h+var_88], rax
0x18002fe2d  movzx   eax, word ptr [rax]
0x18002fe30  mov     [rsp+0D8h+var_80], eax
0x18002fe34  mov     [rsp+0D8h+var_7C], 2
0x18002fe3c  mov     [rsp+0D8h+var_78], r14
0x18002fe41  mov     [rsp+0D8h+var_70], 51h ; 'Q'
0x18002fe49  mov     [rsp+0D8h+var_6C], 1
0x18002fe51  mov     rax, r15
0x18002fe54  sub     eax, r12d
0x18002fe57  mov     [rsp+0D8h+var_A4], eax
0x18002fe5b  mov     eax, [rsp+0D8h+var_A4]
0x18002fe5f  lea     rax, [rsp+0D8h+var_88]
0x18002fe64  mov     [rsp+0D8h+var_B0], rax
0x18002fe69  mov     [rsp+0D8h+var_B8], 4
0x18002fe71  xor     r9d, r9d
0x18002fe74  xor     r8d, r8d
0x18002fe77  lea     rdx, [rsp+0D8h+var_A0]
0x18002fe7c  mov     rcx, [r10+20h]
0x18002fe80  call    cs:__imp_EtwEventWriteTransfer
0x18002fe86  xor     r8d, r8d; struct IPart *
0x18002fe89  xor     edx, edx; struct IMMDevice *
0x18002fe8b  mov     rcx, rdi; this
0x18002fe8e  call    ?RestorePersistedState@CPersistedControl@@QEAAJPEAUIMMDevice@@PEAUIPart@@@Z; CPersistedControl::RestorePersistedState(IMMDevice *,IPart *)
0x18002fe93  jmp     loc_18002FD87
0x18002fe98  mov     rcx, rbp; lpCriticalSection
0x18002fe9b  call    cs:__imp_LeaveCriticalSection
0x18002fea1  mov     rcx, [rsp+0D8h+var_48]
0x18002fea9  xor     rcx, rsp; StackCookie
0x18002feac  call    __security_check_cookie
0x18002feb1  add     rsp, 0A0h
0x18002feb8  pop     r15
0x18002feba  pop     r14
0x18002febc  pop     r12
0x18002febe  pop     rdi
0x18002febf  pop     rsi
0x18002fec0  pop     rbp
0x18002fec1  pop     rbx
0x18002fec2  retn
```
