# AlpcConnection::Callback_ProcessReceivedBuffer(IAlpcConnectionHost *,AlpcBuffer *,_ALPC_MESSAGE_ATTRIBUTES *,bool *,bool *)

- ea: `0x180038b04`
- end: `0x180038cb4`
- name: `?Callback_ProcessReceivedBuffer@AlpcConnection@@AEAAXPEAUIAlpcConnectionHost@@PEAUAlpcBuffer@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEA_N3@Z`
- size: `432`
- prototype: `void __fastcall(AlpcConnection *__hidden this, struct IAlpcConnectionHost *, struct AlpcBuffer *, struct _ALPC_MESSAGE_ATTRIBUTES *, bool *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180074f30`

## callees

- `0x180038b04`
- `0x180038cbc`
- `0x18003950c`
- `0x1800cf010`

## import_xrefs

- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180038b91`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180038c5a`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180038b91`
- `ntdll!RtlSetThreadWorkOnBehalfTicket` at `0x180038c5a`
- `ntdll!RtlGetThreadWorkOnBehalfTicket` at `0x180038c2e`
- `ntdll!RtlGetThreadWorkOnBehalfTicket` at `0x180038c2e`
- `ntdll!AlpcGetMessageAttribute` at `0x180038c13`
- `ntdll!AlpcGetMessageAttribute` at `0x180038c44`
- `ntdll!AlpcGetMessageAttribute` at `0x180038c13`
- `ntdll!AlpcGetMessageAttribute` at `0x180038c44`

## pseudocode

```c
void __fastcall AlpcConnection::Callback_ProcessReceivedBuffer(
        AlpcConnection *this,
        struct IAlpcConnectionHost *a2,
        struct AlpcBuffer *a3,
        struct _ALPC_MESSAGE_ATTRIBUTES *a4,
        bool *a5,
        bool *a6)
{
  bool v6; // zf
  char v11; // si
  int v12; // edi
  char v13; // cl
  _QWORD *MessageAttribute; // rax
  int v15; // eax
  _QWORD v16[3]; // [rsp+20h] [rbp-28h] BYREF
  char *v17; // [rsp+38h] [rbp-10h]
  __int64 v18; // [rsp+80h] [rbp+38h] BYREF

  v6 = (*((_BYTE *)this + 58) & 1) == 0;
  v17 = 0;
  v16[0] = a3;
  v16[1] = 0;
  v16[2] = a4;
  if ( v6 )
    v17 = (char *)this + 104;
  else
    v17 = *(char **)AlpcGetMessageAttribute(a4, 0x20000000);
  v6 = *((_DWORD *)this + 19) == 1;
  *((_QWORD *)this + 8) = v16;
  if ( v6 )
  {
    (*(void (__fastcall **)(AlpcConnection *))(*(_QWORD *)this + 8LL))(this);
    *((_DWORD *)this + 19) = 2;
  }
  v11 = 0;
  v18 = 0;
  if ( (*((_DWORD *)a4 + 1) & 0x2000000) != 0 && (int)RtlGetThreadWorkOnBehalfTicket(&v18, 1) >= 0 )
  {
    MessageAttribute = (_QWORD *)AlpcGetMessageAttribute(a4, 0x2000000);
    if ( v18 != *MessageAttribute )
    {
      RtlSetThreadWorkOnBehalfTicket(MessageAttribute);
      v11 = 1;
    }
  }
  v12 = AlpcConnection::Callback_HandleReceivedBuffer(this, a2, 0, a5);
  if ( v11 )
    RtlSetThreadWorkOnBehalfTicket(&v18);
  if ( v12 == -2018375668 )
  {
    v15 = (*(__int64 (__fastcall **)(struct IAlpcConnectionHost *, _QWORD, _QWORD))(*(_QWORD *)a2 + 16LL))(
            a2,
            *((_QWORD *)v17 + 4),
            *((unsigned int *)v17 + 2));
    if ( v15 < 0 )
      CFlat::Abandonment::FailWithHR(v15, 0, 0);
  }
  else if ( v12 < 0 )
  {
    CFlat::Abandonment::FailWithHR(v12, 0, 0);
  }
  v13 = (*(__int64 (__fastcall **)(AlpcConnection *, struct AlpcBuffer *))(*(_QWORD *)this + 16LL))(this, a3);
  if ( v13 )
  {
    *((_DWORD *)this + 19) = 3;
  }
  else if ( !*((_DWORD *)this + 19) || *((_DWORD *)this + 19) == 3 )
  {
    *((_DWORD *)this + 19) = 1;
  }
  *a6 = v13;
}

```

## disassembly

```asm
0x180038b04  push    rbp
0x180038b06  push    rbx
0x180038b07  push    rsi
0x180038b08  push    rdi
0x180038b09  push    r14
0x180038b0b  push    r15
0x180038b0d  mov     rbp, rsp
0x180038b10  sub     rsp, 48h
0x180038b14  test    byte ptr [rcx+3Ah], 1
0x180038b18  mov     rdi, r9
0x180038b1b  mov     r15, r8
0x180038b1e  mov     [rbp+var_10], 0
0x180038b26  mov     r14, rdx
0x180038b29  mov     [rbp+var_28], r8
0x180038b2d  mov     rbx, rcx
0x180038b30  mov     [rbp+var_20], 0
0x180038b38  mov     [rbp+var_18], r9
0x180038b3c  jnz     loc_180038C0B
0x180038b42  lea     rax, [rcx+68h]
0x180038b46  mov     [rbp+var_10], rax
0x180038b4a  cmp     dword ptr [rbx+4Ch], 1
0x180038b4e  lea     rax, [rbp+var_28]
0x180038b52  mov     [rbx+40h], rax
0x180038b56  jz      loc_180038BE7
0x180038b5c  xor     sil, sil
0x180038b5f  mov     [rbp+arg_0], 0
0x180038b67  test    dword ptr [rdi+4], 2000000h
0x180038b6e  jnz     loc_180038C25
0x180038b74  mov     r9, [rbp+arg_20]; bool *
0x180038b78  xor     r8d, r8d; bool
0x180038b7b  mov     rdx, r14; struct IAlpcConnectionHost *
0x180038b7e  mov     rcx, rbx; this
0x180038b81  call    ?Callback_HandleReceivedBuffer@AlpcConnection@@IEAAJPEAUIAlpcConnectionHost@@_NPEA_N@Z; AlpcConnection::Callback_HandleReceivedBuffer(IAlpcConnectionHost *,bool,bool *)
0x180038b86  mov     edi, eax
0x180038b88  test    sil, sil
0x180038b8b  jz      short loc_180038B97
0x180038b8d  lea     rcx, [rbp+arg_0]
0x180038b91  call    cs:__imp_RtlSetThreadWorkOnBehalfTicket
0x180038b97  cmp     edi, 87B2080Ch
0x180038b9d  jz      loc_180038C77
0x180038ba3  test    edi, edi
0x180038ba5  js      loc_180038CA7
0x180038bab  mov     rax, [rbx]
0x180038bae  mov     rdx, r15
0x180038bb1  mov     rcx, rbx
0x180038bb4  mov     rax, [rax+10h]
0x180038bb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bbd  mov     cl, al
0x180038bbf  test    al, al
0x180038bc1  jnz     short loc_180038C02
0x180038bc3  cmp     dword ptr [rbx+4Ch], 0
0x180038bc7  jnz     loc_180038C68
0x180038bcd  mov     dword ptr [rbx+4Ch], 1
0x180038bd4  mov     rax, [rbp+arg_28]
0x180038bd8  mov     [rax], cl
0x180038bda  add     rsp, 48h
0x180038bde  pop     r15
0x180038be0  pop     r14
0x180038be2  pop     rdi
0x180038be3  pop     rsi
0x180038be4  pop     rbx
0x180038be5  pop     rbp
0x180038be6  retn
0x180038be7  mov     rax, [rbx]
0x180038bea  mov     rcx, rbx
0x180038bed  mov     rax, [rax+8]
0x180038bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bf6  mov     dword ptr [rbx+4Ch], 2
0x180038bfd  jmp     loc_180038B5C
0x180038c02  mov     dword ptr [rbx+4Ch], 3
0x180038c09  jmp     short loc_180038BD4
0x180038c0b  mov     edx, 20000000h
0x180038c10  mov     rcx, rdi
0x180038c13  call    cs:__imp_AlpcGetMessageAttribute
0x180038c19  mov     rcx, [rax]
0x180038c1c  mov     [rbp+var_10], rcx
0x180038c20  jmp     loc_180038B4A
0x180038c25  mov     edx, 1
0x180038c2a  lea     rcx, [rbp+arg_0]
0x180038c2e  call    cs:__imp_RtlGetThreadWorkOnBehalfTicket
0x180038c34  test    eax, eax
0x180038c36  js      loc_180038B74
0x180038c3c  mov     edx, 2000000h
0x180038c41  mov     rcx, rdi
0x180038c44  call    cs:__imp_AlpcGetMessageAttribute
0x180038c4a  mov     rcx, [rbp+arg_0]
0x180038c4e  cmp     rcx, [rax]
0x180038c51  jz      loc_180038B74
0x180038c57  mov     rcx, rax
0x180038c5a  call    cs:__imp_RtlSetThreadWorkOnBehalfTicket
0x180038c60  mov     sil, 1
0x180038c63  jmp     loc_180038B74
0x180038c68  cmp     dword ptr [rbx+4Ch], 3
0x180038c6c  jnz     loc_180038BD4
0x180038c72  jmp     loc_180038BCD
0x180038c77  mov     rdx, [rbp+var_10]
0x180038c7b  mov     rcx, r14
0x180038c7e  mov     rax, [r14]
0x180038c81  mov     r8d, [rdx+8]
0x180038c85  mov     rdx, [rdx+20h]
0x180038c89  mov     rax, [rax+10h]
0x180038c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c92  test    eax, eax
0x180038c94  jns     loc_180038BAB
0x180038c9a  xor     r8d, r8d; int
0x180038c9d  xor     edx, edx; void *
0x180038c9f  mov     ecx, eax; int
0x180038ca1  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
0x180038ca7  xor     r8d, r8d; int
0x180038caa  xor     edx, edx; void *
0x180038cac  mov     ecx, edi; int
0x180038cae  call    ?FailWithHR@Abandonment@CFlat@@SAXHPEAXH@Z; CFlat::Abandonment::FailWithHR(int,void *,int)
```
