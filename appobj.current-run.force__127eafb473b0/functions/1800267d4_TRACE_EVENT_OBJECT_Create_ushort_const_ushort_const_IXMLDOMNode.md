# TRACE_EVENT_OBJECT::Create(ushort const *,ushort const *,IXMLDOMNode *)

- ea: `0x1800267d4`
- end: `0x180026ae3`
- name: `?Create@TRACE_EVENT_OBJECT@@QEAAJPEBG0PEAUIXMLDOMNode@@@Z`
- size: `783`
- prototype: `__int64 __fastcall(TRACE_EVENT_OBJECT *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180028c60`

## callees

- `0x180001fb0`
- `0x180002e90`
- `0x180005ba8`
- `0x1800267d4`
- `0x18002ac98`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## string_xrefs

- `0x180026a38`: `System\TimeCreated`

## pseudocode

```c
__int64 __fastcall TRACE_EVENT_OBJECT::Create(
        TRACE_EVENT_OBJECT *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct IXMLDOMNode *a4)
{
  int v8; // ebx
  struct IXMLDOMNode *v9; // rdx
  struct IXMLDOMNode *v10; // rdx
  struct IXMLDOMNode *v11; // rdx
  struct IXMLDOMNode *v12; // rdx
  struct IXMLDOMNode *v13; // rdx
  void **v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[32]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+60h] [rbp-A0h]
  __int16 v19; // [rsp+64h] [rbp-9Ch]
  int v20; // [rsp+68h] [rbp-98h]
  _BYTE v21[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v22; // [rsp+90h] [rbp-70h]
  int v23; // [rsp+98h] [rbp-68h]
  __int16 v24; // [rsp+9Ch] [rbp-64h]
  int v25; // [rsp+A0h] [rbp-60h]
  __int16 v26; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[510]; // [rsp+B2h] [rbp-4Eh] BYREF
  __int16 v28; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v29[510]; // [rsp+2B2h] [rbp+1B2h] BYREF

  memset_0(v27, 0, sizeof(v27));
  v23 = 512;
  v22 = (unsigned __int16 *)&v26;
  v24 = 256;
  v26 = 0;
  v25 = 0;
  v15 = &APP_OBJECT_UTILS::`vftable';
  memset_0(v29, 0, sizeof(v29));
  v18 = 512;
  v17 = (unsigned __int16 *)&v28;
  v19 = 256;
  v20 = 0;
  v28 = 0;
  if ( a4 && a2 )
  {
    *((_QWORD *)this + 28) = a4;
    ((void (__fastcall *)(struct IXMLDOMNode *))a4->lpVtbl->AddRef)(a4);
    v8 = COMMAND_OBJECT::AddAttribute(this, L"EVENT.NAME", a3);
    if ( v8 >= 0 )
    {
      v8 = COMMAND_OBJECT::AddAttribute(this, L"TRACE.NAME", a2);
      if ( v8 >= 0 )
      {
        *v17 = 0;
        v9 = (struct IXMLDOMNode *)*((_QWORD *)this + 28);
        v20 = 0;
        APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(
          (APP_OBJECT_UTILS *)&v15,
          v9,
          L"System\\EventID",
          0,
          (struct STRU *)v16);
        v8 = COMMAND_OBJECT::AddAttribute(this, L"EventID", v17);
        if ( v8 >= 0 )
        {
          *v17 = 0;
          v10 = (struct IXMLDOMNode *)*((_QWORD *)this + 28);
          v20 = 0;
          APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(
            (APP_OBJECT_UTILS *)&v15,
            v10,
            L"System\\Provider",
            L"Guid",
            (struct STRU *)v16);
          v8 = COMMAND_OBJECT::AddAttribute(this, L"ProviderId", v17);
          if ( v8 >= 0 )
          {
            *v17 = 0;
            v11 = (struct IXMLDOMNode *)*((_QWORD *)this + 28);
            v20 = 0;
            APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(
              (APP_OBJECT_UTILS *)&v15,
              v11,
              L"RenderingInfo\\Opcode",
              0,
              (struct STRU *)v16);
            v8 = COMMAND_OBJECT::AddAttribute(this, L"Name", v17);
            if ( v8 >= 0 )
            {
              *v17 = 0;
              v12 = (struct IXMLDOMNode *)*((_QWORD *)this + 28);
              v20 = 0;
              APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(
                (APP_OBJECT_UTILS *)&v15,
                v12,
                L"System\\Level",
                0,
                (struct STRU *)v16);
              v8 = COMMAND_OBJECT::AddAttribute(this, L"Level", v17);
              if ( v8 >= 0 )
              {
                *v17 = 0;
                v13 = (struct IXMLDOMNode *)*((_QWORD *)this + 28);
                v20 = 0;
                APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(
                  (APP_OBJECT_UTILS *)&v15,
                  v13,
                  L"System\\TimeCreated",
                  L"SystemTime",
                  (struct STRU *)v16);
                v8 = COMMAND_OBJECT::AddAttribute(this, L"Time", v17);
                if ( v8 >= 0 )
                {
                  v8 = STRU::Copy((STRU *)v21, a3);
                  if ( v8 >= 0 )
                    v8 = STRU::Copy((TRACE_EVENT_OBJECT *)((char *)this + 16), v22);
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  BUFFER::~BUFFER((BUFFER *)v16);
  v15 = &APP_OBJECT_UTILS::`vftable';
  BUFFER::~BUFFER((BUFFER *)v21);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800267d4  push    rbp
0x1800267d6  push    rbx
0x1800267d7  push    rsi
0x1800267d8  push    rdi
0x1800267d9  push    r14
0x1800267db  lea     rbp, [rsp-3C0h]
0x1800267e3  sub     rsp, 4C0h
0x1800267ea  mov     rax, cs:__security_cookie
0x1800267f1  xor     rax, rsp
0x1800267f4  mov     [rbp+3E0h+var_30], rax
0x1800267fb  mov     r14, r8
0x1800267fe  mov     rsi, rdx
0x180026801  mov     rdi, rcx
0x180026804  xor     edx, edx; Val
0x180026806  mov     r8d, 1FEh; Size
0x18002680c  lea     rcx, [rbp+3E0h+var_42E]; void *
0x180026810  mov     rbx, r9
0x180026813  call    memset_0
0x180026818  lea     rax, [rbp+3E0h+var_430]
0x18002681c  mov     [rbp+3E0h+var_448], 200h
0x180026823  mov     [rbp+3E0h+var_450], rax
0x180026827  lea     rcx, [rbp+3E0h+var_22E]; void *
0x18002682e  xor     eax, eax
0x180026830  mov     [rbp+3E0h+var_444], 100h
0x180026836  mov     [rbp+3E0h+var_430], ax
0x18002683a  xor     edx, edx; Val
0x18002683c  lea     rax, ??_7APP_OBJECT_UTILS@@6B@; const APP_OBJECT_UTILS::`vftable'
0x180026843  mov     [rbp+3E0h+var_440], 0
0x18002684a  mov     r8d, 1FEh; Size
0x180026850  mov     [rsp+4E0h+var_4B0], rax
0x180026855  call    memset_0
0x18002685a  lea     rax, [rbp+3E0h+var_230]
0x180026861  mov     [rsp+4E0h+var_480], 200h
0x180026869  mov     [rsp+4E0h+var_488], rax
0x18002686e  xor     eax, eax
0x180026870  mov     [rsp+4E0h+var_47C], 100h
0x180026877  mov     [rsp+4E0h+var_478], 0
0x18002687f  mov     [rbp+3E0h+var_230], ax
0x180026886  test    rbx, rbx
0x180026889  jz      loc_180026A9F
0x18002688f  test    rsi, rsi
0x180026892  jz      loc_180026A9F
0x180026898  mov     [rdi+0E0h], rbx
0x18002689f  mov     rcx, rbx
0x1800268a2  mov     rax, [rbx]
0x1800268a5  mov     rax, [rax+8]
0x1800268a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268ae  mov     r8, r14; unsigned __int16 *
0x1800268b1  lea     rdx, aEventName; "EVENT.NAME"
0x1800268b8  mov     rcx, rdi; this
0x1800268bb  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x1800268c0  mov     ebx, eax
0x1800268c2  test    eax, eax
0x1800268c4  js      loc_180026AA4
0x1800268ca  mov     r8, rsi; unsigned __int16 *
0x1800268cd  lea     rdx, aTraceName; "TRACE.NAME"
0x1800268d4  mov     rcx, rdi; this
0x1800268d7  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x1800268dc  mov     ebx, eax
0x1800268de  test    eax, eax
0x1800268e0  js      loc_180026AA4
0x1800268e6  mov     rax, [rsp+4E0h+var_488]
0x1800268eb  lea     r8, aSystemEventid; "System\\EventID"
0x1800268f2  xor     ecx, ecx
0x1800268f4  xor     r9d, r9d; unsigned __int16 *
0x1800268f7  mov     [rax], cx
0x1800268fa  lea     rax, [rsp+4E0h+var_4A8]
0x1800268ff  mov     rdx, [rdi+0E0h]; struct IXMLDOMNode *
0x180026906  mov     [rsp+4E0h+var_478], ecx
0x18002690a  lea     rcx, [rsp+4E0h+var_4B0]; this
0x18002690f  mov     [rsp+4E0h+var_4C0], rax; struct STRU *
0x180026914  call    ?GetNodeOrAttributeValueFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEBG1PEAVSTRU@@@Z; APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(IXMLDOMNode *,ushort const *,ushort const *,STRU *)
0x180026919  mov     r8, [rsp+4E0h+var_488]; unsigned __int16 *
0x18002691e  lea     rdx, aEventid; "EventID"
0x180026925  mov     rcx, rdi; this
0x180026928  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x18002692d  mov     ebx, eax
0x18002692f  test    eax, eax
0x180026931  js      loc_180026AA4
0x180026937  mov     rax, [rsp+4E0h+var_488]
0x18002693c  lea     r9, aGuid; "Guid"
0x180026943  xor     ecx, ecx
0x180026945  lea     r8, aSystemProvider; "System\\Provider"
0x18002694c  mov     [rax], cx
0x18002694f  lea     rax, [rsp+4E0h+var_4A8]
0x180026954  mov     rdx, [rdi+0E0h]; struct IXMLDOMNode *
0x18002695b  mov     [rsp+4E0h+var_478], ecx
0x18002695f  lea     rcx, [rsp+4E0h+var_4B0]; this
0x180026964  mov     [rsp+4E0h+var_4C0], rax; struct STRU *
0x180026969  call    ?GetNodeOrAttributeValueFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEBG1PEAVSTRU@@@Z; APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(IXMLDOMNode *,ushort const *,ushort const *,STRU *)
0x18002696e  mov     r8, [rsp+4E0h+var_488]; unsigned __int16 *
0x180026973  lea     rdx, aProviderid; "ProviderId"
0x18002697a  mov     rcx, rdi; this
0x18002697d  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026982  mov     ebx, eax
0x180026984  test    eax, eax
0x180026986  js      loc_180026AA4
0x18002698c  mov     rax, [rsp+4E0h+var_488]
0x180026991  lea     r8, aRenderinginfoO; "RenderingInfo\\Opcode"
0x180026998  xor     ecx, ecx
0x18002699a  xor     r9d, r9d; unsigned __int16 *
0x18002699d  mov     [rax], cx
0x1800269a0  lea     rax, [rsp+4E0h+var_4A8]
0x1800269a5  mov     rdx, [rdi+0E0h]; struct IXMLDOMNode *
0x1800269ac  mov     [rsp+4E0h+var_478], ecx
0x1800269b0  lea     rcx, [rsp+4E0h+var_4B0]; this
0x1800269b5  mov     [rsp+4E0h+var_4C0], rax; struct STRU *
0x1800269ba  call    ?GetNodeOrAttributeValueFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEBG1PEAVSTRU@@@Z; APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(IXMLDOMNode *,ushort const *,ushort const *,STRU *)
0x1800269bf  mov     r8, [rsp+4E0h+var_488]; unsigned __int16 *
0x1800269c4  lea     rdx, aName; "Name"
0x1800269cb  mov     rcx, rdi; this
0x1800269ce  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x1800269d3  mov     ebx, eax
0x1800269d5  test    eax, eax
0x1800269d7  js      loc_180026AA4
0x1800269dd  mov     rax, [rsp+4E0h+var_488]
0x1800269e2  lea     r8, aSystemLevel; "System\\Level"
0x1800269e9  xor     ecx, ecx
0x1800269eb  xor     r9d, r9d; unsigned __int16 *
0x1800269ee  mov     [rax], cx
0x1800269f1  lea     rax, [rsp+4E0h+var_4A8]
0x1800269f6  mov     rdx, [rdi+0E0h]; struct IXMLDOMNode *
0x1800269fd  mov     [rsp+4E0h+var_478], ecx
0x180026a01  lea     rcx, [rsp+4E0h+var_4B0]; this
0x180026a06  mov     [rsp+4E0h+var_4C0], rax; struct STRU *
0x180026a0b  call    ?GetNodeOrAttributeValueFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEBG1PEAVSTRU@@@Z; APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(IXMLDOMNode *,ushort const *,ushort const *,STRU *)
0x180026a10  mov     r8, [rsp+4E0h+var_488]; unsigned __int16 *
0x180026a15  lea     rdx, aLevel; "Level"
0x180026a1c  mov     rcx, rdi; this
0x180026a1f  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026a24  mov     ebx, eax
0x180026a26  test    eax, eax
0x180026a28  js      short loc_180026AA4
0x180026a2a  mov     rax, [rsp+4E0h+var_488]
0x180026a2f  lea     r9, aSystemtime; "SystemTime"
0x180026a36  xor     ecx, ecx
0x180026a38  lea     r8, aSystemTimecrea; "System\\TimeCreated"
0x180026a3f  mov     [rax], cx
0x180026a42  lea     rax, [rsp+4E0h+var_4A8]
0x180026a47  mov     rdx, [rdi+0E0h]; struct IXMLDOMNode *
0x180026a4e  mov     [rsp+4E0h+var_478], ecx
0x180026a52  lea     rcx, [rsp+4E0h+var_4B0]; this
0x180026a57  mov     [rsp+4E0h+var_4C0], rax; struct STRU *
0x180026a5c  call    ?GetNodeOrAttributeValueFromXML@APP_OBJECT_UTILS@@QEAAJPEAUIXMLDOMNode@@PEBG1PEAVSTRU@@@Z; APP_OBJECT_UTILS::GetNodeOrAttributeValueFromXML(IXMLDOMNode *,ushort const *,ushort const *,STRU *)
0x180026a61  mov     r8, [rsp+4E0h+var_488]; unsigned __int16 *
0x180026a66  lea     rdx, aTime; "Time"
0x180026a6d  mov     rcx, rdi; this
0x180026a70  call    ?AddAttribute@COMMAND_OBJECT@@QEAAJPEBG0@Z; COMMAND_OBJECT::AddAttribute(ushort const *,ushort const *)
0x180026a75  mov     ebx, eax
0x180026a77  test    eax, eax
0x180026a79  js      short loc_180026AA4
0x180026a7b  mov     rdx, r14; unsigned __int16 *
0x180026a7e  lea     rcx, [rsp+4E0h+var_470]; this
0x180026a83  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026a88  mov     ebx, eax
0x180026a8a  test    eax, eax
0x180026a8c  js      short loc_180026AA4
0x180026a8e  mov     rdx, [rbp+3E0h+var_450]; unsigned __int16 *
0x180026a92  lea     rcx, [rdi+10h]; this
0x180026a96  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180026a9b  mov     ebx, eax
0x180026a9d  jmp     short loc_180026AA4
0x180026a9f  mov     ebx, 80070057h
0x180026aa4  lea     rcx, [rsp+4E0h+var_4A8]; this
0x180026aa9  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180026aae  lea     rax, ??_7APP_OBJECT_UTILS@@6B@; const APP_OBJECT_UTILS::`vftable'
0x180026ab5  lea     rcx, [rsp+4E0h+var_470]; this
0x180026aba  mov     [rsp+4E0h+var_4B0], rax
0x180026abf  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180026ac4  mov     eax, ebx
0x180026ac6  mov     rcx, [rbp+3E0h+var_30]
0x180026acd  xor     rcx, rsp; StackCookie
0x180026ad0  call    __security_check_cookie
0x180026ad5  add     rsp, 4C0h
0x180026adc  pop     r14
0x180026ade  pop     rdi
0x180026adf  pop     rsi
0x180026ae0  pop     rbx
0x180026ae1  pop     rbp
0x180026ae2  retn
```
