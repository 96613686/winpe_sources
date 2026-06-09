# FrameWindow::FirePendingMessages(PluginId)

- ea: `0x1800227a0`
- end: `0x180022942`
- name: `?FirePendingMessages@FrameWindow@@AEAAXW4PluginId@@@Z`
- size: `418`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800232e8`
- `0x18002b910`

## callees

- `0x180001900`
- `0x18000193c`
- `0x180006a20`
- `0x180020528`
- `0x1800227a0`
- `0x180022f44`
- `0x18002b298`
- `0x18002c5e0`
- `0x180035010`

## pseudocode

```c
void __fastcall FrameWindow::FirePendingMessages(__int64 a1, __int64 a2)
{
  int v2; // edx
  __int64 v3; // r11
  _QWORD *v4; // r14
  __int64 *v5; // r8
  __int64 *v6; // rbx
  __int64 *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi
  __int64 *v10; // rbp
  __int64 v11; // r15
  void (__fastcall ***v12)(_QWORD, __int64); // rax
  _QWORD *v13; // rdx
  __int64 v14; // rax
  __int64 **v15; // rdx
  __int64 *v16; // rcx
  __int64 *v17; // rax
  __int64 *i; // rdx
  char **v19; // rbx
  int v20; // [rsp+78h] [rbp+10h] BYREF
  void (__fastcall ***v21)(_QWORD, __int64); // [rsp+80h] [rbp+18h] BYREF

  v20 = a2;
  if ( (unsigned __int8)FrameWindow::IsPluginLoaded(a1, a2) )
  {
    v4 = (_QWORD *)(v3 + 464);
    v5 = *(__int64 **)(v3 + 464);
    v6 = v5;
    v7 = (__int64 *)v5[1];
    while ( !*((_BYTE *)v7 + 25) )
    {
      if ( *((_DWORD *)v7 + 8) >= v2 )
      {
        v6 = v7;
        v7 = (__int64 *)*v7;
      }
      else
      {
        v7 = (__int64 *)v7[2];
      }
    }
    if ( !*((_BYTE *)v6 + 25) && v2 >= *((_DWORD *)v6 + 8) && v6 != v5 )
    {
      v8 = (_QWORD *)v6[5];
      v9 = (_QWORD *)v6[6];
      if ( v8 != v9 )
      {
        v10 = (__int64 *)(v3 + 448);
        do
        {
          v11 = **(_QWORD **)std::map<enum PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](v10, &v20);
          v12 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x20u);
          v21 = v12;
          v13 = v12;
          *((_DWORD *)v12 + 2) = 18;
          *((_DWORD *)v12 + 3) = -1;
          *v12 = (void (__fastcall **)(_QWORD, __int64))&PluginMessageFireJsonMessageEvent::`vftable';
          v12[2] = 0;
          v12[3] = 0;
          v14 = v8[1];
          if ( v14 )
            _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
          v13[2] = *v8;
          v13[3] = v8[1];
          v21 = (void (__fastcall ***)(_QWORD, __int64))v13;
          BrowserToolThread::PostPluginMessage(v11, &v21);
          if ( v21 )
            (**v21)(v21, 1);
          v8 += 2;
        }
        while ( v8 != v9 );
      }
      v15 = (__int64 **)v6[2];
      if ( *((_BYTE *)v15 + 25) )
      {
        v16 = (__int64 *)v6[1];
        v17 = v6;
        while ( !*((_BYTE *)v16 + 25) && v17 == (__int64 *)v16[2] )
        {
          v17 = v16;
          v16 = (__int64 *)v16[1];
        }
      }
      else
      {
        for ( i = *v15; !*((_BYTE *)i + 25); i = (__int64 *)*i )
          ;
      }
      v19 = (char **)std::_Tree_val<std::_Tree_simple_types<std::pair<enum PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>>::_Extract(
                       v4,
                       v6);
      std::vector<std::shared_ptr<PluginPendingMessage>>::_Tidy(v19 + 5);
      operator delete(v19);
    }
  }
}

```

## disassembly

```asm
0x1800227a0  mov     [rsp+arg_0], rbx
0x1800227a5  mov     [rsp+arg_8], edx
0x1800227a9  push    rbp
0x1800227aa  push    rsi
0x1800227ab  push    rdi
0x1800227ac  push    r14
0x1800227ae  push    r15
0x1800227b0  sub     rsp, 40h
0x1800227b4  mov     r11, rcx
0x1800227b7  call    ?IsPluginLoaded@FrameWindow@@AEBA_NW4PluginId@@@Z; FrameWindow::IsPluginLoaded(PluginId)
0x1800227bc  test    al, al
0x1800227be  jz      loc_180022931
0x1800227c4  lea     r14, [r11+1D0h]
0x1800227cb  xor     ecx, ecx
0x1800227cd  mov     r8, [r14]
0x1800227d0  mov     rbx, r8
0x1800227d3  mov     rax, [r8+8]
0x1800227d7  jmp     short loc_1800227EA
0x1800227d9  cmp     [rax+20h], edx
0x1800227dc  jge     short loc_1800227E4
0x1800227de  mov     rax, [rax+10h]
0x1800227e2  jmp     short loc_1800227EA
0x1800227e4  mov     rbx, rax
0x1800227e7  mov     rax, [rax]
0x1800227ea  cmp     [rax+19h], cl
0x1800227ed  jz      short loc_1800227D9
0x1800227ef  cmp     [rbx+19h], cl
0x1800227f2  jnz     loc_180022931
0x1800227f8  cmp     edx, [rbx+20h]
0x1800227fb  jl      loc_180022931
0x180022801  cmp     rbx, r8
0x180022804  jz      loc_180022931
0x18002280a  mov     rdi, [rbx+28h]
0x18002280e  mov     rsi, [rbx+30h]
0x180022812  cmp     rdi, rsi
0x180022815  jz      loc_1800228D0
0x18002281b  lea     rbp, [r11+1C0h]
0x180022822  lea     rdx, [rsp+68h+arg_8]
0x180022827  mov     rcx, rbp
0x18002282a  call    ??A?$map@W4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@U?$less@W4PluginId@@@3@V?$allocator@U?$pair@$$CBW4PluginId@@V?$shared_ptr@UBrowserToolThreadInfo@@@std@@@std@@@3@@std@@QEAAAEAV?$shared_ptr@UBrowserToolThreadInfo@@@1@AEBW4PluginId@@@Z; std::map<PluginId,std::shared_ptr<BrowserToolThreadInfo>>::operator[](PluginId const &)
0x18002282f  mov     rcx, [rax]
0x180022832  mov     r15, [rcx]
0x180022835  mov     ecx, 20h ; ' '; Size
0x18002283a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002283f  mov     [rsp+68h+arg_10], rax
0x180022847  mov     rdx, rax
0x18002284a  mov     dword ptr [rax+8], 12h
0x180022851  mov     dword ptr [rax+0Ch], 0FFFFFFFFh
0x180022858  lea     rax, ??_7PluginMessageFireJsonMessageEvent@@6B@; const PluginMessageFireJsonMessageEvent::`vftable'
0x18002285f  mov     [rdx], rax
0x180022862  mov     qword ptr [rdx+10h], 0
0x18002286a  mov     qword ptr [rdx+18h], 0
0x180022872  mov     rax, [rdi+8]
0x180022876  test    rax, rax
0x180022879  jz      short loc_18002287F
0x18002287b  lock inc dword ptr [rax+8]
0x18002287f  mov     rax, [rdi]
0x180022882  mov     rcx, r15
0x180022885  mov     [rdx+10h], rax
0x180022889  mov     rax, [rdi+8]
0x18002288d  mov     [rdx+18h], rax
0x180022891  mov     [rsp+68h+arg_10], rdx
0x180022899  lea     rdx, [rsp+68h+arg_10]
0x1800228a1  call    ?PostPluginMessage@BrowserToolThread@@QEBAJ$$QEAV?$unique_ptr@UPluginMessageInfo@@U?$default_delete@UPluginMessageInfo@@@std@@@std@@@Z; BrowserToolThread::PostPluginMessage(std::unique_ptr<PluginMessageInfo> &&)
0x1800228a6  mov     rcx, [rsp+68h+arg_10]
0x1800228ae  test    rcx, rcx
0x1800228b1  jz      short loc_1800228C3
0x1800228b3  mov     rax, [rcx]
0x1800228b6  mov     edx, 1
0x1800228bb  mov     rax, [rax]
0x1800228be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228c3  add     rdi, 10h
0x1800228c7  cmp     rdi, rsi
0x1800228ca  jnz     loc_180022822
0x1800228d0  mov     rdx, [rbx+10h]
0x1800228d4  cmp     byte ptr [rdx+19h], 0
0x1800228d8  jz      short loc_1800228F8
0x1800228da  mov     rcx, [rbx+8]
0x1800228de  mov     rax, rbx
0x1800228e1  jmp     short loc_1800228F0
0x1800228e3  cmp     rax, [rcx+10h]
0x1800228e7  jnz     short loc_18002290D
0x1800228e9  mov     rax, rcx
0x1800228ec  mov     rcx, [rcx+8]
0x1800228f0  cmp     byte ptr [rcx+19h], 0
0x1800228f4  jz      short loc_1800228E3
0x1800228f6  jmp     short loc_18002290D
0x1800228f8  mov     rdx, [rdx]
0x1800228fb  cmp     byte ptr [rdx+19h], 0
0x1800228ff  jnz     short loc_18002290D
0x180022901  mov     rax, [rdx]
0x180022904  mov     rdx, rax
0x180022907  cmp     byte ptr [rax+19h], 0
0x18002290b  jz      short loc_180022901
0x18002290d  mov     rdx, rbx
0x180022910  mov     rcx, r14
0x180022913  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>>,std::_Iterator_base0>)
0x180022918  mov     rbx, rax
0x18002291b  lea     rcx, [rax+28h]
0x18002291f  call    ?_Tidy@?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<PluginPendingMessage>>::_Tidy(void)
0x180022924  mov     edx, 40h ; '@'
0x180022929  mov     rcx, rbx; Block
0x18002292c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022931  mov     rbx, [rsp+68h+arg_0]
0x180022936  add     rsp, 40h
0x18002293a  pop     r15
0x18002293c  pop     r14
0x18002293e  pop     rdi
0x18002293f  pop     rsi
0x180022940  pop     rbp
0x180022941  retn
```
